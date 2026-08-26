---
name: Read EVEDEX market data without credentials
description: Discover tradable instruments, check whether the venue is halted, and pull historical candlesticks — the entire read path, no authentication needed.
api: openapi/evedex-market-data-openapi.json
operations:
  - "GET /api/history/{instrument}/list"
  - "GET /api/market"
  - "GET /api/market/instrument"
generated: '2026-08-26'
method: generated
source: https://docs.evedex.com/developers/developers/market_data
---

# Read EVEDEX market data

This is the one EVEDEX surface that needs no credential and no wallet. Start here.

## 1. Check the venue is actually trading

`GET /api/market` on `https://exchange-api.evedex.com` returns a `state` field.

Only `active` means trading. `request-status-fail`, `me-dead` and `db-admin-dead` are **global
halts** — not a per-instrument condition, and not something you can work around by retrying a
different symbol. Stop and report.

## 2. Find a tradable instrument

`GET /api/market/instrument` returns every registered instrument, including ones you cannot trade.
Filter on the `trading` field before doing anything with a symbol:

- `all` — tradable.
- `onlyClose` — you may close positions and cancel orders, but not open anything new.
- `restricted` / `none` — treat as unavailable for **any** order.

Instrument names are plain symbols, e.g. `BTCUSD`.

## 3. Pull history

`GET /api/history/{instrument}/list` on `https://market-data-api.evedex.com`:

- `after` / `before` — inclusive ISO 8601 bounds.
- `group` — one of `1s 1m 3m 5m 15m 30m 1h 4h 6h 12h 1d 1w 1mo`.

The response is an array of **positional tuples**, not objects:

```
[ timestamp_ms, open, close, high, low, volumeUsd, volume ]
```

Note the order: **open, close, high, low** — not the OHLC order most charting libraries assume.
Mapping this wrong is silent; you get a plausible chart with the wrong candles.

A single response returns at most **100,000** candlesticks. Page with `after`/`before` if your
range is larger; there is no cursor and no total-count field.

## Staying current

For the currently-forming candle, subscribe to the Centrifugo channel
`market-data:last-candlestick-{instrument}-{timeframe}` — same tuple shape. See
`asyncapi/evedex-centrifugo-events.yml`.

## Rate limits

Read operations are not counted against the 30-per-60-second heavy-request budget, which covers
only writes. No rate-limit headers are returned, so pace yourself conservatively.
