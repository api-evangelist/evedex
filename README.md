# EVEDEX

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

EVEDEX is a hybrid decentralized perpetual-futures exchange built on Arbitrum (Layer 3) that pairs an off-chain order book and matching engine with on-chain settlement and full self-custody, so users trade at centralized-exchange latency without surrendering their keys. Its public developer program spans eleven live OpenAPI 3.1.0 services totalling 557 operations — Auth, Exchange, Market Data, Referral/Affiliate, Notifications, Academy, Game, Billing, Bridge Middleware, AI Strategies and Backoffice — all published from a single Swagger UI at swagger.evedex.com. Authentication is either an X-API-Key issued from the exchange UI or a short-lived JWT minted through EIP-4361 Sign-In with Ethereum, and every write that moves value (order creation, replacement, position closure, withdrawal) additionally requires an EIP-712 typed-data signature from the user's own wallet. Asynchronous state is delivered over seventeen documented Centrifugo WebSocket channels using a snapshot-plus-updates consistency pattern. EVEDEX ships an official TypeScript SDK (@evedex/exchange-bot-sdk) with separate demo and production containers, and publishes agent-native documentation via llms.txt and per-page markdown with a GitBook ask-parameter query interface.

**Areas:** Cryptocurrency Exchange · DeFi · Decentralized Exchange · Derivatives · Perpetual Futures · Trading · Market Data · Blockchain · Web3 · arbitrum-layer3 · Fintech

## EVEDEX on APIs.io

Everything profiled for EVEDEX is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/evedex/](https://apis.io/providers/evedex/)** — or go straight to one of the APIs or properties below.

### APIs (109)

- [EVEDEX Documentation & Agent Surface](https://apis.io/apis/evedex/evedex-documentation-agent-surface/) — The GitBook developer portal and agent-native documentation surface. Every page is retrievable as markdown by appending .md, llms.txt indexes the full…
- [EVEDEX Async API (Centrifugo)](https://apis.io/apis/evedex/evedex-async-api-centrifugo/) — Real-time exchange events over WebSocket, brokered by Centrifugo with JWT channel access rights and epoch-based state recovery. Seventeen documented…
- [EVEDEX ACL API](https://apis.io/apis/evedex/evedex-acl-api/) — The ACL API from EVEDEX — 3 operation(s) for acl.
- [EVEDEX AI Strategy API](https://apis.io/apis/evedex/evedex-ai-strategy-api/) — The AI Strategy API from EVEDEX — 5 operation(s) for ai strategy.
- [EVEDEX Aml API](https://apis.io/apis/evedex/evedex-aml-api/) — The Aml API from EVEDEX — 3 operation(s) for aml.
- [EVEDEX Article API](https://apis.io/apis/evedex/evedex-article-api/) — The Article API from EVEDEX — 2 operation(s) for article.
- [EVEDEX Auth API](https://apis.io/apis/evedex/evedex-auth-api/) — The Auth API from EVEDEX — 11 operation(s) for auth.
- [EVEDEX Badge API](https://apis.io/apis/evedex/evedex-badge-api/) — The Badge API from EVEDEX — 10 operation(s) for badge.
- [EVEDEX Bill API](https://apis.io/apis/evedex/evedex-bill-api/) — The Bill API from EVEDEX — 5 operation(s) for bill.
- [EVEDEX Blocked API](https://apis.io/apis/evedex/evedex-blocked-api/) — The Blocked API from EVEDEX — 3 operation(s) for blocked.
- [EVEDEX Bot API](https://apis.io/apis/evedex/evedex-bot-api/) — The Bot API from EVEDEX — 6 operation(s) for bot.
- [EVEDEX Cashback API](https://apis.io/apis/evedex/evedex-cashback-api/) — The Cashback API from EVEDEX — 2 operation(s) for cashback.
- [EVEDEX Centrifugo API](https://apis.io/apis/evedex/evedex-centrifugo-api/) — The Centrifugo API from EVEDEX — 1 operation(s) for centrifugo.
- [EVEDEX Challenges API](https://apis.io/apis/evedex/evedex-challenges-api/) — The Challenges API from EVEDEX — 10 operation(s) for challenges.
- [EVEDEX Checkout API](https://apis.io/apis/evedex/evedex-checkout-api/) — The Checkout API from EVEDEX — 1 operation(s) for checkout.
- [EVEDEX Claim stop list API](https://apis.io/apis/evedex/evedex-claim-stop-list-api/) — The Claim stop list API from EVEDEX — 1 operation(s) for claim stop list.
- [EVEDEX Coin API](https://apis.io/apis/evedex/evedex-coin-api/) — The Coin API from EVEDEX — 2 operation(s) for coin.
- [EVEDEX Collectable API](https://apis.io/apis/evedex/evedex-collectable-api/) — The Collectable API from EVEDEX — 5 operation(s) for collectable.
- [EVEDEX Comment API](https://apis.io/apis/evedex/evedex-comment-api/) — The Comment API from EVEDEX — 2 operation(s) for comment.
- [EVEDEX Competition Templates API](https://apis.io/apis/evedex/evedex-competition-templates-api/) — The Competition Templates API from EVEDEX — 3 operation(s) for competition templates.
- [EVEDEX Competitions API](https://apis.io/apis/evedex/evedex-competitions-api/) — The Competitions API from EVEDEX — 8 operation(s) for competitions.
- [EVEDEX Course API](https://apis.io/apis/evedex/evedex-course-api/) — The Course API from EVEDEX — 10 operation(s) for course.
- [EVEDEX Curator Course API](https://apis.io/apis/evedex/evedex-curatorcourse-api/) — The CuratorCourse API from EVEDEX — 2 operation(s) for curatorcourse.
- [EVEDEX Daily Statistics API](https://apis.io/apis/evedex/evedex-dailystatistics-api/) — The DailyStatistics API from EVEDEX — 1 operation(s) for dailystatistics.
- [EVEDEX Daily Task API](https://apis.io/apis/evedex/evedex-dailytask-api/) — The DailyTask API from EVEDEX — 3 operation(s) for dailytask.
- [EVEDEX Deposit API](https://apis.io/apis/evedex/evedex-deposit-api/) — The Deposit API from EVEDEX — 1 operation(s) for deposit.
- [EVEDEX Deposit Bonus API](https://apis.io/apis/evedex/evedex-deposit-bonus-api/) — The Deposit Bonus API from EVEDEX — 4 operation(s) for deposit bonus.
- [EVEDEX Dev API](https://apis.io/apis/evedex/evedex-dev-api/) — The Dev API from EVEDEX — 10 operation(s) for dev.
- [EVEDEX Discord API](https://apis.io/apis/evedex/evedex-discord-api/) — The Discord API from EVEDEX — 3 operation(s) for discord.
- [EVEDEX Distribution API](https://apis.io/apis/evedex/evedex-distribution-api/) — The Distribution API from EVEDEX — 5 operation(s) for distribution.
- [EVEDEX Event API](https://apis.io/apis/evedex/evedex-event-api/) — The Event API from EVEDEX — 3 operation(s) for event.
- [EVEDEX Exchange API](https://apis.io/apis/evedex/evedex-exchange-api/) — The Exchange API from EVEDEX — 5 operation(s) for exchange.
- [EVEDEX External API](https://apis.io/apis/evedex/evedex-external-api/) — The External API from EVEDEX — 3 operation(s) for external.
- [EVEDEX File API](https://apis.io/apis/evedex/evedex-file-api/) — The File API from EVEDEX — 10 operation(s) for file.
- [EVEDEX Funded Account API](https://apis.io/apis/evedex/evedex-funded-account-api/) — The Funded Account API from EVEDEX — 3 operation(s) for funded account.
- [EVEDEX Grand Contest API](https://apis.io/apis/evedex/evedex-grandcontest-api/) — The GrandContest API from EVEDEX — 7 operation(s) for grandcontest.
- [EVEDEX Hedging API](https://apis.io/apis/evedex/evedex-hedging-api/) — The Hedging API from EVEDEX — 2 operation(s) for hedging.
- [EVEDEX History API](https://apis.io/apis/evedex/evedex-history-api/) — The History API from EVEDEX — 5 operation(s) for history.
- [EVEDEX Homework API](https://apis.io/apis/evedex/evedex-homework-api/) — The Homework API from EVEDEX — 2 operation(s) for homework.
- [EVEDEX Invitation API](https://apis.io/apis/evedex/evedex-invitation-api/) — The Invitation API from EVEDEX — 1 operation(s) for invitation.
- [EVEDEX Journal API](https://apis.io/apis/evedex/evedex-journal-api/) — The Journal API from EVEDEX — 1 operation(s) for journal.
- [EVEDEX Leaderboard API](https://apis.io/apis/evedex/evedex-leaderboard-api/) — The Leaderboard API from EVEDEX — 7 operation(s) for leaderboard.
- [EVEDEX League API](https://apis.io/apis/evedex/evedex-league-api/) — The League API from EVEDEX — 1 operation(s) for league.
- [EVEDEX Lesson API](https://apis.io/apis/evedex/evedex-lesson-api/) — The Lesson API from EVEDEX — 2 operation(s) for lesson.
- [EVEDEX Link API](https://apis.io/apis/evedex/evedex-link-api/) — The Link API from EVEDEX — 7 operation(s) for link.
- [EVEDEX Liquidation API](https://apis.io/apis/evedex/evedex-liquidation-api/) — The Liquidation API from EVEDEX — 1 operation(s) for liquidation.
- [EVEDEX Lucky Shot API](https://apis.io/apis/evedex/evedex-lucky-shot-api/) — The Lucky Shot API from EVEDEX — 8 operation(s) for lucky shot.
- [EVEDEX Mail API](https://apis.io/apis/evedex/evedex-mail-api/) — The Mail API from EVEDEX — 1 operation(s) for mail.
- [EVEDEX Market API](https://apis.io/apis/evedex/evedex-market-api/) — The Market API from EVEDEX — 9 operation(s) for market.
- [EVEDEX Material API](https://apis.io/apis/evedex/evedex-material-api/) — The Material API from EVEDEX — 2 operation(s) for material.
- [EVEDEX Message API](https://apis.io/apis/evedex/evedex-message-api/) — The Message API from EVEDEX — 4 operation(s) for message.
- [EVEDEX Module API](https://apis.io/apis/evedex/evedex-module-api/) — The Module API from EVEDEX — 2 operation(s) for module.
- [EVEDEX Newcomer API](https://apis.io/apis/evedex/evedex-newcomer-api/) — The Newcomer API from EVEDEX — 2 operation(s) for newcomer.
- [EVEDEX Notification API](https://apis.io/apis/evedex/evedex-notification-api/) — The Notification API from EVEDEX — 1 operation(s) for notification.
- [EVEDEX Notifications API](https://apis.io/apis/evedex/evedex-notifications-api/) — The Notifications API from EVEDEX — 6 operation(s) for notifications.
- [EVEDEX Order API](https://apis.io/apis/evedex/evedex-order-api/) — The Order API from EVEDEX — 15 operation(s) for order.
- [EVEDEX Paysystem API](https://apis.io/apis/evedex/evedex-paysystem-api/) — The Paysystem API from EVEDEX — 1 operation(s) for paysystem.
- [EVEDEX Podium API](https://apis.io/apis/evedex/evedex-podium-api/) — The Podium API from EVEDEX — 4 operation(s) for podium.
- [EVEDEX Points API](https://apis.io/apis/evedex/evedex-points-api/) — The Points API from EVEDEX — 4 operation(s) for points.
- [EVEDEX Position API](https://apis.io/apis/evedex/evedex-position-api/) — The Position API from EVEDEX — 4 operation(s) for position.
- [EVEDEX Product API](https://apis.io/apis/evedex/evedex-product-api/) — The Product API from EVEDEX — 3 operation(s) for product.
- [EVEDEX Public profile API](https://apis.io/apis/evedex/evedex-public-profile-api/) — The Public profile API from EVEDEX — 2 operation(s) for public profile.
- [EVEDEX Push API](https://apis.io/apis/evedex/evedex-push-api/) — The Push API from EVEDEX — 1 operation(s) for push.
- [EVEDEX Quest API](https://apis.io/apis/evedex/evedex-quest-api/) — The Quest API from EVEDEX — 4 operation(s) for quest.
- [EVEDEX Question API](https://apis.io/apis/evedex/evedex-question-api/) — The Question API from EVEDEX — 2 operation(s) for question.
- [EVEDEX Redirect API](https://apis.io/apis/evedex/evedex-redirect-api/) — The Redirect API from EVEDEX — 6 operation(s) for redirect.
- [EVEDEX Referral API](https://apis.io/apis/evedex/evedex-referral-api/) — The Referral API from EVEDEX — 1 operation(s) for referral.
- [EVEDEX Referral Competition API](https://apis.io/apis/evedex/evedex-referralcompetition-api/) — The ReferralCompetition API from EVEDEX — 1 operation(s) for referralcompetition.
- [EVEDEX Refund API](https://apis.io/apis/evedex/evedex-refund-api/) — The Refund API from EVEDEX — 1 operation(s) for refund.
- [EVEDEX Registration request API](https://apis.io/apis/evedex/evedex-registration-request-api/) — The Registration request API from EVEDEX — 3 operation(s) for registration request.
- [EVEDEX Reward API](https://apis.io/apis/evedex/evedex-reward-api/) — The Reward API from EVEDEX — 8 operation(s) for reward.
- [EVEDEX Rhino API](https://apis.io/apis/evedex/evedex-rhino-api/) — The Rhino API from EVEDEX — 2 operation(s) for rhino.
- [EVEDEX Service API](https://apis.io/apis/evedex/evedex-service-api/) — The Service API from EVEDEX — 2 operation(s) for service.
- [EVEDEX Session API](https://apis.io/apis/evedex/evedex-session-api/) — The Session API from EVEDEX — 5 operation(s) for session.
- [EVEDEX Share Content API](https://apis.io/apis/evedex/evedex-sharecontent-api/) — The ShareContent API from EVEDEX — 2 operation(s) for sharecontent.
- [EVEDEX Simulator API](https://apis.io/apis/evedex/evedex-simulator-api/) — The Simulator API from EVEDEX — 2 operation(s) for simulator.
- [EVEDEX Skill API](https://apis.io/apis/evedex/evedex-skill-api/) — The Skill API from EVEDEX — 6 operation(s) for skill.
- [EVEDEX Smart Account API](https://apis.io/apis/evedex/evedex-smartaccount-api/) — The SmartAccount API from EVEDEX — 2 operation(s) for smartaccount.
- [EVEDEX Statistics API](https://apis.io/apis/evedex/evedex-statistics-api/) — The Statistics API from EVEDEX — 6 operation(s) for statistics.
- [EVEDEX Statistics details API](https://apis.io/apis/evedex/evedex-statistics-details-api/) — The Statistics details API from EVEDEX — 2 operation(s) for statistics details.
- [EVEDEX Statistics List API](https://apis.io/apis/evedex/evedex-statistics-list-api/) — The Statistics List API from EVEDEX — 3 operation(s) for statistics list.
- [EVEDEX Strategy API](https://apis.io/apis/evedex/evedex-strategy-api/) — The Strategy API from EVEDEX — 4 operation(s) for strategy.
- [EVEDEX Subscription API](https://apis.io/apis/evedex/evedex-subscription-api/) — The Subscription API from EVEDEX — 4 operation(s) for subscription.
- [EVEDEX Subtitle API](https://apis.io/apis/evedex/evedex-subtitle-api/) — The Subtitle API from EVEDEX — 2 operation(s) for subtitle.
- [EVEDEX System API](https://apis.io/apis/evedex/evedex-system-api/) — The System API from EVEDEX — 2 operation(s) for system.
- [EVEDEX Tag API](https://apis.io/apis/evedex/evedex-tag-api/) — The Tag API from EVEDEX — 5 operation(s) for tag.
- [EVEDEX Tariff API](https://apis.io/apis/evedex/evedex-tariff-api/) — The Tariff API from EVEDEX — 4 operation(s) for tariff.
- [EVEDEX Telegram API](https://apis.io/apis/evedex/evedex-telegram-api/) — The Telegram API from EVEDEX — 5 operation(s) for telegram.
- [EVEDEX Template API](https://apis.io/apis/evedex/evedex-template-api/) — The Template API from EVEDEX — 2 operation(s) for template.
- [EVEDEX Tp Sl API](https://apis.io/apis/evedex/evedex-tpsl-api/) — The TpSl API from EVEDEX — 3 operation(s) for tpsl.
- [EVEDEX Trade signal API](https://apis.io/apis/evedex/evedex-trade-signal-api/) — The Trade signal API from EVEDEX — 2 operation(s) for trade signal.
- [EVEDEX Trading Platform API](https://apis.io/apis/evedex/evedex-trading-platform-api/) — The Trading Platform API from EVEDEX — 5 operation(s) for trading platform.
- [EVEDEX Trading Competition API](https://apis.io/apis/evedex/evedex-tradingcompetition-api/) — The TradingCompetition API from EVEDEX — 1 operation(s) for tradingcompetition.
- [EVEDEX Trading Volume API](https://apis.io/apis/evedex/evedex-tradingvolume-api/) — The TradingVolume API from EVEDEX — 1 operation(s) for tradingvolume.
- [EVEDEX Transfer API](https://apis.io/apis/evedex/evedex-transfer-api/) — The Transfer API from EVEDEX — 8 operation(s) for transfer.
- [EVEDEX User API](https://apis.io/apis/evedex/evedex-user-api/) — The User API from EVEDEX — 74 operation(s) for user.
- [EVEDEX User Image API](https://apis.io/apis/evedex/evedex-userimage-api/) — The UserImage API from EVEDEX — 1 operation(s) for userimage.
- [EVEDEX Wallet API](https://apis.io/apis/evedex/evedex-wallet-api/) — The Wallet API from EVEDEX — 1 operation(s) for wallet.
- [EVEDEX Webhook API](https://apis.io/apis/evedex/evedex-webhook-api/) — The Webhook API from EVEDEX — 3 operation(s) for webhook.
- [EVEDEX Winner API](https://apis.io/apis/evedex/evedex-winner-api/) — The Winner API from EVEDEX — 1 operation(s) for winner.
- [EVEDEX Withdraw API](https://apis.io/apis/evedex/evedex-withdraw-api/) — The Withdraw API from EVEDEX — 3 operation(s) for withdraw.
- [EVEDEX Yield API](https://apis.io/apis/evedex/evedex-yield-api/) — The Yield API from EVEDEX — 2 operation(s) for yield.
- [EVEDEX OAUTH API](https://apis.io/apis/evedex/evedex-oauth-api/) — The Oauth API from EVEDEX — 5 operation(s) for oauth.
- [EVEDEX API Key API](https://apis.io/apis/evedex/evedex-api-key-api/) — The API Key API from EVEDEX — 3 operation(s) for api key.
- [EVEDEX Mobile App API](https://apis.io/apis/evedex/evedex-mobile-app-api/) — The Mobile App API from EVEDEX — 9 operation(s) for mobile app.
- [EVEDEX Payment Service API](https://apis.io/apis/evedex/evedex-payment-service-api/) — The Payment Service API from EVEDEX — 1 operation(s) for payment service.
- [EVEDEX Promo Codes API](https://apis.io/apis/evedex/evedex-promo-codes-api/) — The Promo Codes API from EVEDEX — 4 operation(s) for promo codes.
- [EVEDEX Short Link API](https://apis.io/apis/evedex/evedex-short-link-api/) — The Short Link API from EVEDEX — 3 operation(s) for short link.
- [EVEDEX Sub Account API](https://apis.io/apis/evedex/evedex-sub-account-api/) — The Sub Account API from EVEDEX — 7 operation(s) for sub account.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Evedex Centrifugo Events](https://apis.io/asyncapis/evedex/evedex-centrifugo-events/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [evedex-mcp.yml](https://apis.io/servers/evedex/evedex-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Evedex Agentic Access](https://apis.io/agentic-access/evedex/evedex-agentic-access/)

#### Overlays (11)

OpenAPI overlays, including conversational phrasing for each operation.

- [Evedex Academy Overlay](https://apis.io/overlays/evedex/evedex-academy-overlay/)
- [Evedex Ai Strategies Overlay](https://apis.io/overlays/evedex/evedex-ai-strategies-overlay/)
- [Evedex Auth Overlay](https://apis.io/overlays/evedex/evedex-auth-overlay/)
- [Evedex Backoffice Overlay](https://apis.io/overlays/evedex/evedex-backoffice-overlay/)
- [Evedex Billing Overlay](https://apis.io/overlays/evedex/evedex-billing-overlay/)
- [Evedex Bridge Middleware Overlay](https://apis.io/overlays/evedex/evedex-bridge-middleware-overlay/)
- [Evedex Exchange Overlay](https://apis.io/overlays/evedex/evedex-exchange-overlay/)
- [Evedex Game Overlay](https://apis.io/overlays/evedex/evedex-game-overlay/)
- [Evedex Market Data Overlay](https://apis.io/overlays/evedex/evedex-market-data-overlay/)
- [Evedex Notifications Overlay](https://apis.io/overlays/evedex/evedex-notifications-overlay/)
- [Evedex Referral Overlay](https://apis.io/overlays/evedex/evedex-referral-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Evedex Authentication](https://apis.io/security/evedex/evedex-authentication/)
- [Evedex Domain Security](https://apis.io/security/evedex/evedex-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Evedex Plans Pricing](https://apis.io/plans/evedex/evedex-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Evedex Rate Limits](https://apis.io/rate-limits/evedex/evedex-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://evedex.com/)
- [Documentation](https://docs.evedex.com/developers/developers)
- [Getting started](https://docs.evedex.com/developers/developers/toolkit)
- [API reference](https://swagger.evedex.com/)
- [Pricing](https://docs.evedex.com/key-features-and-components/trading-platform-and-matching-engine/trading-fees)
- [Sign up](https://exchange.evedex.com/)
- [Support](https://help.evedex.com/)
- [Blog](https://blog.evedex.com/)
- [Terms of service](https://docs.evedex.com/legal/global/terms-of-use-global)
- [Privacy policy](https://docs.evedex.com/legal/global/privacy-policy-global)
- [GitHub](https://github.com/evedex-official)
- [Status](https://status.evedex.com/)

## API Evangelist rating

**Kin Score 56.3** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 51.5 |
| Contract governance | 4.5 |
| Operational transparency | 55.3 |
| Developer ergonomics | 73.2 |
| Access clarity | 63.2 |

**Agent readiness 35.8** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | mostly |

**Regulatory alignment 28.7** — Securities & Market Data

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/evedex/](https://apis.io/providers/evedex/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for EVEDEX: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/evedex/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
