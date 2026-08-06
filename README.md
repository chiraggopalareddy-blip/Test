# Institutional Buy/Sell Confluence (TradingView)

Pine Script v5 indicator that fires **BUY / SELL** only when multiple institutional-style factors align.

> No indicator has guaranteed “institutional accuracy.” This script scores confluence (structure, HTF bias, volume, order blocks, liquidity sweeps, trend stack) and only signals when the score clears your threshold.

## File

- [`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## How to use on TradingView

1. Open TradingView → Pine Editor
2. Paste the contents of `InstitutionalBuySell.pine`
3. Click **Add to chart**
4. Best on liquid symbols (indices, futures, large-cap stocks) on **5m / 15m / 1H**

## What it measures (score 0–6)

| Factor | Buy side | Sell side |
|--------|----------|-----------|
| Market structure / BOS–CHoCH | Bullish structure break | Bearish structure break |
| Higher-timeframe bias | Price above HTF EMA | Price below HTF EMA |
| Relative volume | High volume on green bar | High volume on red bar |
| Order block retest | Price revisits bullish OB | Price revisits bearish OB |
| Liquidity sweep | Sweep of lows + reclaim | Sweep of highs + reject |
| EMA stack + RSI | 8 > 21 > 50 + RSI mid | 8 < 21 < 50 + RSI mid |

Default **minimum score = 4**. Raise it for fewer, higher-quality signals.

## Recommended settings

- **Intraday indices (NIFTY / BANKNIFTY):** HTF = `60`, Min Score = `4` or `5`, Rel Vol ≥ `1.4`
- **Swing stocks:** HTF = `D`, chart TF = `1H` or `4H`, Min Score = `4`
- Turn **Show Weak / Watch Signals** on if you want early triangles before full confluence

## Alerts

Three alert conditions are built in:

- Institutional BUY
- Institutional SELL
- Any Institutional Signal

Create the alert from the chart → Alerts → Condition = this indicator.

## Important limits

- Uses **public chart data only** (price + volume). It does **not** read broker order flow, dark pools, or exchange OI.
- For strike-level CE/PE OI charts (like your earlier request), TradingView data is often incomplete — this indicator is for price-action confluence, not option-chain OI.
- Always combine with risk management; past confluence does not guarantee future results.
