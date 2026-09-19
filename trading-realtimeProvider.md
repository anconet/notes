# Trading Realtime Provider
[Return to Home](readMe.md)

Focused comparison for day trading needs: real-time 1s/1min bars, Level 2, and volume/float data.

## Requirements for Day Trading
- Real-time (not delayed) quotes and trades
- 1 second and 1 minute bar/candle data
- Level 2 (market depth / order book)
- Volume and float data
- WebSocket streaming (polling is too slow for scanning)

## Comparison

| Provider | Free Tier Real-Time | Level 2 | 1min/1s Data | WebSocket Streaming | Rate Limits (Free) | Cost for Real-Time | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Yahoo Finance (`yahoo-finance2`) | Mostly delayed/unofficial | No | Limited, delayed | No (unofficial polling only) | Unofficial, can break anytime | N/A - not a supported product | Good for historical/EOD data and prototyping only |
| Finnhub | Real-time for US stocks on free tier (trades via websocket) | No (not on free/lower tiers) | Yes, 1min candles on free tier | Yes | 60 calls/min free tier | Paid plans for higher limits/more data | Best low-cost entry into real-time trade data |
| Polygon.io | Delayed 15min on free tier | Yes, on paid plans | Yes, 1s aggregates on paid plans | Yes | 5 calls/min on free tier | Starter plan ~$29-$99/mo for real-time; Level 2 requires higher tier | Best for serious/production day trading scanners |

## Recommendation
- Prototype scanner logic and UI: Yahoo Finance (free, easy, historical data)
- Add real-time trade/quote streaming on a budget: Finnhub (free tier websocket)
- Production scanner with Level 2 and sub-minute bars: Polygon.io (paid tier required)

## Open Questions
- Confirm current Finnhub free tier limits (rate limits and coverage change over time)
- Confirm which Polygon plan tier includes Level 2 data

## Float Data
- Float is largely static (changes only via buybacks, secondary offerings, insider lockup expirations), so it's fundamentals/reference data, not a streaming need
- Available from company profile/fundamentals endpoints on all three providers (Finnhub `stock/metric`, Polygon ticker details, Yahoo quote summary)
- Can be fetched infrequently (e.g. daily) and cached rather than polled/streamed

