# Institutional Algo Buy/Sell (TradingView)

5m **intraday A+ scalp** system. Buy/Sell zones unchanged. Trade Idea fills **only** on a live A+ setup.

## File

[`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## Right-side trade tables

**A+ Trade Ideas** (middle-right) — fills only on a live A+ Long/Short; else `-`.

**Risky Trades** (bottom-right) — high risk / high reward ideas (OR/VWAP breakouts, near-A+ zone attempts, momentum stretch). Wider targets toward projected day high/low. Fills only when a risky setup is live; else `-`. Cleared if an A+ takes over.

Both show: Trade · Entry · Stop · Target 1 · Target 2 · Confidence (`xx.x%`).

## Signals (5m scalping)

Session-only (default `0915-1525`), non-repainting, score ≥ **88**:

1. **Primary:** liquidity sweep + reclaim inside Buy/Sell Zone + rejection + volume + bias  
2. **Backup:** confirmed pivot in zone + rejection + RSI + volume + bias  

Strict BUY → SELL alternation within the day. Resets each new session.

## Zones

Unchanged — VWAP σ + Opening Range + prior day liquidity bands.

## Dashboard (top-right)

Live Bias · Projected Day Bias · What to do? · Projected Day High/Low · Day Range  
(all small, same font)

## Use

1. Chart timeframe: **5 minutes**
2. Paste into Pine Editor → Add to chart
3. Set **Intraday Session** for your market if not NSE
4. Wait for A+ BUY/SELL — Trade Idea fills automatically
