# Institutional Algo Buy/Sell (TradingView)

5m **intraday A+ scalp** system. Buy/Sell zones unchanged. Trade Idea fills **only** on a live A+ setup.

## File

[`indicators/InstitutionalBuySell.pine`](indicators/InstitutionalBuySell.pine)

## Optional panels (checkboxes)

**Show Last A+ / Risky Trade Tables** — left-side tables:
- Last A+ Trade
- Last Risky Trade  

Stores the most recently suggested plan (stays after the live idea clears).

**Show Shadow Candle Projection** — draws translucent projected candles for the full session from the open (gap direction + ADR projected high/low). Enable only when you want the path overlay; disable to clear.


## Signals (5m scalping)

Session-only (default `0915-1525`), non-repainting, score ≥ **88**:

1. **Primary:** liquidity sweep + reclaim inside Buy/Sell Zone + rejection + volume + bias  
2. **Backup:** confirmed pivot in zone + rejection + RSI + volume + bias  

Strict BUY → SELL alternation within the day. Resets each new session.

## Zones

Unchanged — VWAP σ + Opening Range + prior day liquidity bands.

## Dashboard (top-right)

Live Bias · Projected Day Bias · Control · Futures OI · OI Regime (x3) · OI Read · What to do? · Projected Day High/Low · Day Range  

**Futures OI:** reads NSE daily OI from `NSE:NIFTY1!_OI` (service symbol). Change **Futures Symbol** in settings if needed. True options-chain CE/PE OI is not available in Pine.

## Use

1. Chart timeframe: **5 minutes**
2. Paste into Pine Editor → Add to chart
3. Set **Intraday Session** for your market if not NSE
4. Wait for A+ BUY/SELL — Trade Idea fills automatically
