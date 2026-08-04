# DEGIRO

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

DEGIRO is a European discount brokerage platform offering retail investors access to stocks, ETFs, bonds, options, futures, warrants, and investment funds across 50+ exchanges in 30 countries. Founded in the Netherlands in 2013, DEGIRO is known for among the lowest trading commissions in Europe and is regulated by the Dutch Authority for the Financial Markets (AFM) and De Nederlandsche Bank (DNB).

## APIs

DEGIRO does not provide an official public API. The DEGIRO trading platform exposes REST-style HTTP endpoints used internally by the web and mobile trading applications. These endpoints have been documented by the developer community through reverse engineering and are available via multiple open-source client libraries.

### Trading API

Session-authenticated REST API for account management, portfolio operations, and order execution. Supports:

- **Authentication**: Username/password login with optional TOTP two-factor authentication; session-based (JSESSIONID cookie); 30-minute session timeout
- **Account Management**: Account configuration, client details, account state and info
- **Portfolio**: Current positions, open orders, pending orders, cash funds
- **Order Management**: Create, update, delete, and retrieve orders (LIMIT, MARKET, STOP_LOSS, STOP_LOSS_LIMIT types; DAY or PERMANENT duration)
- **Transaction History**: Historical trades and orders (90-day maximum window per query)
- **Favorites and Notes**: Manage watchlists and annotate instruments
- **Upcoming Payments**: Dividend and payment schedule retrieval

### Product Search API

Endpoint suite for discovering tradable instruments:

- Full-text search across all asset classes
- Filter by exchange, index, product type
- Retrieve product details: ISIN, currency, exchange, pricing metadata
- Batch retrieval by product IDs
- Asset classes: shares, ETFs, bonds, options, futures, warrants, leveraged products, investment funds, CFDs

### Quotecast API (Real-Time Market Data)

Real-time streaming data via the vwd Quotecast protocol:

- Live ticker subscriptions for price, volume, bid/ask, OHLC
- Chart data with multiple time resolutions
- Historical price series
- Products referenced by vwd_id or issueid
- Connection resets every ~15 seconds; requires re-subscription

### Reporting API

Downloadable account reports and statements:

- Formats: CSV, HTML, PDF, XLS
- Account statements, transaction records, order history
- Portfolio snapshots and cash movement history

### News and Company Intelligence API

Company research and market intelligence via Refinitiv and vwd data:

- Company news feeds
- Company profiles and financial ratios
- Income statements, balance sheets, cash flow statements
- Analyst estimates and price targets
- Corporate event agendas: earnings, dividends, IPOs, stock splits

## Pricing

DEGIRO charges per-trade commissions with no monthly account fees, no inactivity fees, and no custody fees.

| Asset Class | Fee |
|---|---|
| Stocks (home exchange) | EUR 2-4.90 + EUR 1 handling |
| Stocks (US markets) | EUR 2 + EUR 1 handling |
| ETFs (Core Selection, Tradegate) | EUR 1 (first monthly trade per ETF free) |
| ETFs (non-Core) | EUR 3 + EUR 1 handling |
| Options | EUR 0.75/contract + EUR 1 handling |
| Futures | EUR 0.50/contract + EUR 1 handling |
| Bonds | EUR 2 + EUR 1 handling |
| Currency conversion (auto) | 0.25% of transaction |
| Margin financing | 3% per annum |

## Resources

- Website: https://www.degiro.eu
- Login: https://trader.degiro.nl/login
- Support: https://www.degiro.eu/contact
- Terms of Service: https://www.degiro.eu/terms-conditions
- Community API (Python): https://github.com/Chavithra/degiro-connector
- Community API (Python async): https://github.com/ohmajesticlama/degiroasync
- Community API (TypeScript): https://github.com/icastillejogomez/degiro-api

## Important Disclaimer

DEGIRO does not provide or support an official API. The endpoints documented here are internal platform APIs discovered through reverse engineering. DEGIRO may change or block these endpoints without notice. Use of automated trading scripts may violate DEGIRO's Terms of Service and could result in account suspension. This catalog is provided for informational and research purposes only.
