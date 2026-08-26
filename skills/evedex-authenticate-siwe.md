---
name: Authenticate to EVEDEX with Sign-In with Ethereum
description: Obtain and maintain an EVEDEX access token using the EIP-4361 SIWE flow, or use an API key, and keep the short-lived token refreshed.
api: openapi/evedex-auth-openapi.json
operations:
  - "GET /auth/nonce"
  - "POST /auth/user/sign-up"
  - "POST /auth/refresh"
  - "POST /auth/revoke"
generated: '2026-08-26'
method: generated
source: https://docs.evedex.com/developers/developers/authorization
---

# Authenticate to EVEDEX

EVEDEX has two credentials and they are not interchangeable. Choose before you start.

**API key** — created by a human in the exchange UI (Settings > API > Create API Key), sent as
`x-api-key: <key>` on every private request. Long-lived. Cannot be minted through the API.

**SIWE JWT** — minted programmatically from a wallet signature. Short-lived (a few minutes) and
must be refreshed. This is the flow below.

> An API key alone is **not** enough to trade. Order creation, order replacement, position closure
> and withdrawal each require an EIP-712 wallet signature in the request body regardless of which
> credential authenticates the call. See `evedex-place-and-cancel-order`.

## Get a token

1. `GET /auth/nonce` on `https://auth-api.evedex.com` → `{ nonce }`.
2. Build an EIP-4361 SIWE message containing the wallet address, `uri`, `version`, `chainId`,
   the `nonce` from step 1, and `issuedAt` as an ISO 8601 timestamp.
3. Sign it with the user's wallet (`signer.signMessage`).
4. `POST /auth/user/sign-up` with `{ wallet, message, nonce, signature }` → the response `token`
   field is your JWT.

Send it as `Authorization: Bearer <accessToken>` — the word `Bearer`, one space, then the raw
token with no braces.

## Keep it alive

The access token expires in **minutes**, so a `401` is the normal steady state on any session that
runs longer than a few minutes, not an error to alarm on.

- On `401` from any authorized operation: `POST /auth/refresh` with
  `Authorization: Bearer <refreshToken>`. A success returns a new token to replace **both** the
  access and refresh token you were holding.
- On `401` from `/auth/refresh` itself: the refresh token is dead. Start again at step 1.

Do not retry the original request more than once per refresh. If a refresh succeeds and the retry
still 401s, the problem is authorization (403-shaped), not expiry.

## Finish cleanly

`POST /auth/revoke` ends the session. Do this when an agent run completes rather than leaving a
live token behind.

## Errors

Every error is `{"message": "..."}` with no code — see `errors/evedex-problem-types.yml`. `451`
means the caller's jurisdiction is blocked and is never retryable.
