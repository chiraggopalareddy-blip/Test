# Institutional Algo Buy/Sell (TradingView)

Non-repainting major-swing system with live/day bias, projections, top-notch zones, and a trade-idea panel.

## File

[`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## Top-right dashboard

| Field | Meaning |
|-------|---------|
| Live Bias | Bullish / Extremely Bullish / Neutral / Chop / Bearish / Extremely Bearish |
| Projected Day Bias | Session structure bias (OR break + VWAP + ADR travel) |
| What to do? | Buy on dips / Sell on rips / fade range / wait |
| Projected Day High/Low | ADR + Opening-Range expansion hybrid |
| Day Range | Projected high − low |

All table text uses the same small font size.

## Bottom-right — Current Trade Idea

Trade · Entry · Stop · Target 1 · Target 2 · Confidence (`xx.x%`)  
(R:R removed)

## Zones

Buy/Sell zones are narrow ATR-width liquidity bands from:

- Session VWAP ± 1σ
- Opening Range high/low
- Prior day high/low

Snapped to session liquidity after the opening range locks — not full-chart slabs.

## Signals

- Confirmed pivots only (default Left 8 / Right 4) — **no repaint**
- Min swing by ATR **and** ADR fraction → bigger moves only
- Must touch Buy/Sell zone
- Strict BUY → SELL alternation
- Trend gate blocks weak counter-trend fakes
- Score ≥ 80 to print

## Use

Paste into TradingView Pine Editor → Add to chart (5m/15m recommended).  
Still too many signals? Raise **Pivot Left** to `10` and **Min Swing ATR** to `1.8`.
