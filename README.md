# Institutional Algo Buy/Sell (TradingView)

Non-repainting Pine Script v5 system: confirmed swing pivots only, strict BUY→SELL alternation, day projections, and trade plan tables.

## File

[`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## Engine (why fewer fakes)

- **No early signals** — only `ta.pivothigh` / `ta.pivotlow` after `Pivot Right` bars close
- **No repaint** — label is fixed on the swing bar once confirmed; it does not move later
- **Alternation** — BUY must be followed by SELL (and reverse)
- **Min swing + min reverse (ATR)** — ignores tiny noise pivots and mid-trend blips
- **Location filter** — prefers day/OR/projection extremes (BUY ZONE / SELL ZONE)
- **Trend gate** — in strong ADX trends, blocks weak counter-trend pivots unless exhaustion + rejection/divergence
- **Score ≥ 70** required to print

## Dashboards

**Top-right:** Bias · Projected Day Range · Projected Day High/Low · What to do?  
**Bottom-right:** Trade (Long/Short) · Entry · Stop · Target 1 & 2 · Confidence · R:R

Bias values: `Buy` | `Sell` | `Neutral` | `Chop` | `Extremely Bullish` | `Extremely Bearish`

## How to trade it

1. Paste into Pine Editor → Add to chart (5m/15m on liquid symbols)
2. Wait for a **BUY** or **SELL** label (appears a few bars after the true swing — by design)
3. Use bottom-right **Entry / Stop / T1 / T2**
4. Follow **What to do?** until flat, then wait for the opposite side

## Important

Confirmed tops/bottoms always need a few bars after the turn. That lag is what prevents fake mid-candle signals and repainting. If still too many signals, raise **Min Swing (ATR)** to `1.3` and **Pivot Left** to `7`.
