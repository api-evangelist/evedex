---
name: Place and cancel an EVEDEX order safely
description: Submit a signed limit or market order, confirm it actually executed, and cancel it while that is still possible — including what cannot be undone.
api: openapi/evedex-exchange-openapi.json
operations:
  - "POST /api/v2/order/limit"
  - "POST /api/v2/order/market"
  - "GET /api/order"
  - "GET /api/order/{orderId}"
  - "DELETE /api/order/{orderId}"
  - "POST /api/order/mass-cancel"
generated: '2026-08-26'
method: generated
source: https://docs.evedex.com/developers/developers/order_creation
---

# Place and cancel an EVEDEX order

This skill moves real money on a leveraged venue. Read the reversibility section before the
happy path.

## What cannot be undone

- A **filled** order cannot be unwound. There is no reverse, void or refund on a trade.
- A **market order** (`POST /api/v2/order/market`) fills immediately by design. Treat submitting
  one as irreversible from the moment you send it.
- A **withdrawal** has no user-facing recall.
- A **resting** limit or stop-limit order *is* cancellable — until it fills.

EVEDEX supports **no idempotency key** and **no dry-run mode**. If a write times out you cannot
safely retry it; you must read state back (step 5) and decide from what you observe.

## 1. Pre-flight

Confirm `GET /api/market` returns `state: active` and the instrument's `trading` is `all`. Confirm
the notional is at least **5 USD** — below that the order is rejected.

## 2. Mint an orderId

API v2 requires a client-generated id: `<days_since_2025-07-24>:<uuid_without_dashes>`, matching
`[0-9]{5}:[0-9A-Fa-f]{26}` — e.g. `00008:418f0157db5345688b1c910d08`. The day prefix is 5 digits
with leading zeros; the uuid part is 26 hex characters.

For **batch** creation the day prefix must be no earlier than midnight yesterday, or the request
fails with `Invalid order ID date`. Mint ids at send time, not at plan time.

## 3. Sign it — the step that fails most often

Every order carries a `signature` field: an **EIP-712** signature over the typed order data, made
by the wallet sending it. Use `ethers` `Signer.signTypedData`, with the domain and type schemas
EVEDEX publishes at
`github.com/evedex-official/exchange-crypto/blob/master/src/utils/crypto.ts`.

**Normalize every float to an integer before signing:**

```
normalizeNumber = Round(floatValue * 10^8, HalfUp)
```

Round **Down** instead, always, for trading-balance withdrawals. Sign the transformed data, not
the original. A signature over unnormalized floats is well-formed and will be rejected.

EVEDEX rejects the order if the signature is missing, not EIP-712, made by a wallet other than the
sender, or covers data that differs from what you sent.

## 4. Submit

- `POST /api/v2/order/limit` — resting order. `timeInForce` is `GTC` and cannot be changed via API.
- `POST /api/v2/order/market` — `IOC` by default (fills what it can, cancels the rest) or `FOK`
  (all-or-nothing). Irreversible.

## 5. Confirm — a 2xx is not an execution

A `NEW` status means the order **entered the order book**. Nothing more. Execution is asynchronous.

Confirm by reading `GET /api/order/{orderId}` or `GET /api/order`, or by subscribing to the
`order-{userExchangeId}` Centrifugo channel before you submit. Fees arrive later still, on
`order-fee-{userExchangeId}` — the REST `fee` field lags.

## 6. Cancel

- `DELETE /api/order/{orderId}` — one order.
- `POST /api/order/mass-cancel` — every order on an instrument.
- `POST /api/order/mass-cancel-by-id` — a named set.

**Cancellation needs no signature.** The window is the fill: if the order fills before your cancel
is processed, the cancel returns successfully and the status is simply **not** changed to
`CANCELLED`. Always re-read the order after cancelling; do not assume a 2xx means it was cancelled.

## Budget

Order create, cancel, replace, position close, TP/SL mutations and withdrawal all count against
**30 heavy requests per 60 seconds per account**. Max 500 active regular orders and 500 active
TP/SL orders. No `Retry-After` or rate-limit header is returned — count locally.
