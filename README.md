# Institutional Buy/Sell System (TradingView)

Pine Script v5 system for **when** and **where** to buy/sell on the current chart timeframe.

## File

- [`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## What changed (v2)

- **Alternating signals only:** BUY → SELL → BUY → … (no consecutive same-side signals)
- **Fewer false signals:** confirmed swing pivots + zone + RSI/Stoch + rejection + VWAP stretch score
- **Tops/bottoms:** signals prefer confirmed pivot highs/lows (marked on the actual turn bar)
- **Bias table (top-right):** Extremely Bullish / Bullish / Neutral / Bearish / Extremely Bearish from **chart timeframe** EMAs + DMI/ADX + VWAP stretch
- **Dynamic intraday zones:** BUY ZONE and SELL ZONE update through the session (Opening Range + session VWAP bands + day high/low)

## How to use

1. Paste into TradingView Pine Editor → Add to chart
2. Prefer liquid symbols on **5m / 15m**
3. Read the dashboard:
   - **BIAS** = directional conviction on this TF
   - **Next** = which side is allowed next
   - **Buy Zone / Sell Zone** = where to look for the next entry
4. Take **BUY** only in/near the green BUY ZONE when a BUY label prints; take **SELL** only in/near the red SELL ZONE

## Suggested settings

| Goal | Pivot L/R | Min Score | Notes |
|------|-----------|-----------|--------|
| Fewer signals | 4 / 4 | 5 | More confirmation, more lag |
| Tighter tops/bottoms | 2 / 2 | 4 | Faster, more signals |
| Very strict | 3 / 3 | 5 + Require Divergence ON | Highest quality filter |

## Limits

- Exact tops/bottoms cannot be known in advance; this confirms turns after `Pivot Right` bars (default 3).
- Zones and bias use price/volume/VWAP only — not broker order flow or option OI.
- Always use stops (e.g. beyond zone / last swing) and position sizing.
