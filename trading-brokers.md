# Trading Brokers
[Return to Home](readMe.md)

Research on brokers with API access for order execution (buy/sell), as opposed to data-only providers (see [trading-realtimeProvider.md](trading-realtimeProvider.md)).

## Requirements
- API access for placing/managing orders (not just a web UI)
- Support for our target account size (~$500) and SMB day trading
- Low/no commission
- Ideally provides its own market data too, to reduce number of integrations

## Comparison

| Broker | Commission | API | Own Market Data | Min Account | Notes |
| --- | --- | --- | --- | --- | --- |
| Alpaca | Commission-free | Yes, API-first, easy REST/websocket | Yes (real-time + historical) | No minimum | Popular for algo/day trading, good docs, pairs well with a small account |
| Interactive Brokers (IBKR) | Low commission | Yes, TWS API / Client Portal API | Yes | Varies by account type | Full-featured, more complex to integrate, good for options/futures/forex |
| TD Ameritrade / Schwab API | Commission-free equities | Yes | Yes | No minimum | Now merged under Schwab; API migration ongoing, worth checking current status |
| TradeStation | Commission-free/low | Yes | Yes, built-in scanning | Varies | Combines scanning + execution in one platform |

## Recommendation
- Alpaca is the strongest fit for our use case: commission-free, API-first, no minimum account size, and offers its own data feed (could simplify combining scanning + execution).
- Use Finnhub/Polygon for scanning signals, then route the actual order through Alpaca (or another broker's API).

## Open Questions
- Confirm Alpaca's data feed quality (real-time vs delayed) compares to Finnhub/Polygon for our scanner needs
- Confirm current commission/fee structure (can change over time)
- Check pattern day trader (PDT) rule implications for a $500 account
