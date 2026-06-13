# DEGIRO

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
