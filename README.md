# MEXC (mexc)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

MEXC is a global cryptocurrency exchange providing REST and WebSocket APIs for spot trading, perpetual futures, market data, order management, account management, and wallet operations across 1,200+ trading pairs. MEXC supports institutional users through a Broker API with sub-account management and a Market Maker Program with tiered rate limits and competitive fee schedules.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mexc/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mexc/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Cryptocurrency
- Exchange
- Trading
- Futures
- Market Data
- Finance
- Blockchain

## Timestamps

- **Created:** 2026-06-13
- **Modified:** 2026-06-13

## APIs

### MEXC Spot REST API

The MEXC Spot REST API (v3) provides programmatic access to MEXC's spot exchange, supporting over 1,200 cryptocurrency trading pairs. Developers can retrieve real-time and historical market data, manage orders, query account balances, and handle wallet operations including deposits, withdrawals, and address management. Authentication uses HMAC SHA256 signed requests with API key credentials provided via the X-MEXC-APIKEY header. The API enforces IP-based and UID-based rate limits of 300 and 500 weight units per 10-second window respectively.

- **Human URL:** [https://mexcdevelop.github.io/apidocs/spot_v3_en/](https://mexcdevelop.github.io/apidocs/spot_v3_en/)
- **Base URL:** `https://api.mexc.com`

#### Tags

- Cryptocurrency
- Exchange
- Market Data
- Spot
- Trading

#### Properties

- [Documentation](https://mexcdevelop.github.io/apidocs/spot_v3_en/)

### MEXC Spot WebSocket Streams

The MEXC Spot WebSocket Streams deliver real-time market data and user account updates via persistent WebSocket connections. Public channels provide ticker data, order book depth, trade feeds, and kline/candlestick streams. Private (authenticated) channels deliver order status updates and account balance changes. Each connection supports a maximum of 30 channel subscriptions, with a rate limit of 100 messages per second. Connections are valid for up to 24 hours and require periodic ping/pong keepalives.

- **Human URL:** [https://mexcdevelop.github.io/apidocs/spot_v3_en/#websocket-market-streams](https://mexcdevelop.github.io/apidocs/spot_v3_en/#websocket-market-streams)
- **Base URL:** `wss://wbs-api.mexc.com/ws`

#### Tags

- Cryptocurrency
- Market Data
- Real-Time
- Streaming
- WebSocket

#### Properties

- [Documentation](https://mexcdevelop.github.io/apidocs/spot_v3_en/#websocket-market-streams)

### MEXC Futures REST API

The MEXC Futures REST API provides access to MEXC's perpetual futures trading platform. Public endpoints expose contract details, order book depth, index prices, fair prices, funding rates, k-line data, and transaction history without authentication. Authenticated endpoints support account asset management, position management, order placement and cancellation, leverage and margin adjustments, trigger orders, and stop-limit orders. Authentication uses HMAC SHA256 with the ApiKey, Request-Time, and Signature headers. Standard rate limits apply at 20 requests per 2-second window. API Futures trading is subject to a separate fee schedule: maker 0.06% and taker 0.08% as of June 1, 2026.

- **Human URL:** [https://mexcdevelop.github.io/apidocs/contract_v1_en/](https://mexcdevelop.github.io/apidocs/contract_v1_en/)
- **Base URL:** `https://contract.mexc.com`

#### Tags

- Cryptocurrency
- Derivatives
- Exchange
- Futures
- Trading

#### Properties

- [Documentation](https://mexcdevelop.github.io/apidocs/contract_v1_en/)

### MEXC Futures WebSocket API

The MEXC Futures WebSocket API streams real-time derivatives market data and account events over persistent WebSocket connections. Public channels include ticker data, trade transactions, order book depth, k-line streams, and funding rate updates. Private channels (requiring login) stream order status changes, position updates, asset balance changes, and ADL level alerts. The API uses the same base domain as the Futures REST API and supports both public and authenticated channel subscriptions in a single connection.

- **Human URL:** [https://mexcdevelop.github.io/apidocs/contract_v1_en/#websocket-api](https://mexcdevelop.github.io/apidocs/contract_v1_en/#websocket-api)
- **Base URL:** `wss://contract.mexc.com/edge`

#### Tags

- Cryptocurrency
- Derivatives
- Futures
- Real-Time
- Streaming
- WebSocket

#### Properties

- [Documentation](https://mexcdevelop.github.io/apidocs/contract_v1_en/#websocket-api)

### MEXC Broker API

The MEXC Broker API enables institutional partners to manage sub-accounts and provide trading services to their users. MEXC supports three broker modes: API Broker for copy-trading and trading bot platforms, Independent Broker for wallet and market-data aggregation platforms, and OAuth Broker for third-party applications using OAuth 2.0. Brokers can create and manage sub-accounts, generate deposit addresses, process withdrawals, enable futures for sub-accounts, perform universal transfers between spot and futures accounts, and track rebate history. Up to 30 sub-accounts can be maintained per master account.

- **Human URL:** [https://mexcdevelop.github.io/apidocs/](https://mexcdevelop.github.io/apidocs/)
- **Base URL:** `https://api.mexc.com`

#### Tags

- Account Management
- Broker
- Cryptocurrency
- Enterprise
- Sub-Account

#### Properties

- [Documentation](https://mexcdevelop.github.io/apidocs/)

## Common Properties

- [Portal](https://www.mexc.com/mexc-api)
- [Documentation](https://mexcdevelop.github.io/apidocs/spot_v3_en/)
- [Getting Started](https://www.mexc.com/api-docs/spot-v3/introduction)
- [GitHub Organization](https://github.com/mexcdevelop)
- [SDKs](https://github.com/mexcdevelop/mexc-api-sdk)
- [Plans](plans/mexc-plans-pricing.yml)
- [Rate Limits](rate-limits/mexc-rate-limits.yml)
- [FinOps](finops/mexc-finops.yml)
- [Announcements](https://www.mexc.com/announcements/api-updates)
- [Support](https://t.me/MEXC_API)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
