# 🛡️ SqueezeGuard AI Demo

## Demo Scenario

A trader sees a cryptocurrency rapidly increasing in price and considers opening a SHORT position simply because the market already appears overextended.

Before entering the trade, the trader asks:

`I want to SHORT BTCUSDT. Run SqueezeGuard first.`

SqueezeGuard then uses Binance Agent OS to retrieve current Binance Futures market data.

---

## Data Analyzed

SqueezeGuard attempts to retrieve:

- Current price
- 24H change
- 5m candles
- 15m candles
- 1H candles
- Funding rate
- Open interest
- Long/short ratio
- Taker buy/sell volume
- Futures order book

---

## Demo Prompt

Using Binance Agent OS, act as SqueezeGuard AI.

Analyze BTCUSDT USDⓈ-M Futures.

Retrieve current market data including:

- Current price
- 24H change
- Recent 5m candles
- Recent 15m candles
- Recent 1H candles
- Funding rate
- Open interest
- Long/short positioning
- Taker buy/sell volume
- Futures order book

Calculate:

1. SHORT SQUEEZE RISK from 0–100
2. LONG SQUEEZE RISK from 0–100

Use the SqueezeGuard scoring model.

Return:

- Risk scores
- Risk classifications
- Market snapshot
- Supporting evidence
- Counter-evidence
- Critical market level
- Guard Verdict

The scores are heuristic risk scores, not probabilities.

Market-data only.

Do not place, modify, or cancel any transaction.

---

## Expected Output

Example:

# 🛡️ SQUEEZEGUARD AI

Symbol: BTCUSDT

Market: Binance USDⓈ-M Futures

SHORT SQUEEZE RISK:

82/100 — HIGH

LONG SQUEEZE RISK:

24/100 — LOW

Supporting Evidence:

1. Price momentum is strongly bullish.
2. Open interest is expanding.
3. Taker buyers dominate recent flow.
4. Resistance has been broken.

Counter Evidence:

1. Higher-timeframe resistance remains nearby.

GUARD VERDICT:

🔴 HIGH RISK

Opening a new counter-trend SHORT is currently exposed to elevated squeeze risk.

SqueezeGuard provides market-risk intelligence, not guaranteed market predictions.

---

# Demo Safety

The demo uses Binance market data only.

No orders are executed.

No account balances are required.

No assets are transferred.
