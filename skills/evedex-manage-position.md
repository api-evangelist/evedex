---
name: Manage an EVEDEX position
description: Read open positions, adjust leverage reversibly, and close a position — knowing which of those you can take back.
api: openapi/evedex-exchange-openapi.json
operations:
  - "GET /api/position"
  - "PUT /api/position/{instrument}"
  - "POST /api/v2/position/{instrument}/close"
  - "POST /api/transfer/pf/withdraw"
generated: '2026-08-26'
method: generated
source: https://docs.evedex.com/developers/developers/order_creation
---

# Manage an EVEDEX position

## Read

`GET /api/position` lists open positions. Use the snapshot-plus-updates pattern: subscribe to
`position-{userExchangeId}` **first**, then read REST, then merge on the latest `updatedAt`.
Reading first and subscribing second can drop an update in the gap.

## Change leverage — reversible

`PUT /api/position/{instrument}` with the new leverage. **No signature required.** This is the one
position operation you can simply undo: call it again with the previous value. Read the current
leverage first so you have something to restore to.

Leverage is bounded per the spec (`minimum: 1`, `maximum: 300` on the order schema). Raising it
raises liquidation risk on an already-open position — there is no confirmation step.

## Close — not reversible

`POST /api/v2/position/{instrument}/close`, specifying the volume to close. Requires an **EIP-712
signature** (schema at
`github.com/evedex-official/exchange-crypto/blob/master/src/utils/crypto.ts`), with all floats
normalized via `Round(value * 10^8, HalfUp)` before signing.

Settles on execution. There is no reopen and no undo — reopening is a new signed order at whatever
the market then is. Counts against the 30-per-60-second heavy-request budget.

## Withdraw — not reversible

`POST /api/transfer/pf/withdraw` with currency, amount, recipient wallet and signature. Round
**Down**, not HalfUp, when normalizing withdrawal amounts.

- Only **unreserved** funds are eligible — anything tied to a position or open order is not.
- The request is pre-validated and, if funds are available, **your trading account is locked until
  the operation completes**. Do not fire this concurrently with trading activity.
- There is no recall. An operator-side reject exists in EVEDEX's internal Backoffice service; it is
  not available to you.

## If a write times out

EVEDEX offers no idempotency key, so a retry may double-execute. Do not retry. Read back with
`GET /api/position` (or `GET /api/order`) and decide from observed state.
