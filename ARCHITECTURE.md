# 🛡️ SqueezeGuard AI Architecture

SqueezeGuard AI is a market-risk intelligence agent powered by Binance Agent OS.

Its purpose is to detect conditions that may expose traders to short squeezes or long squeezes before they enter a risky counter-trend position.

---

# System Flow

USER
  |
  v
SQUEEZEGUARD AI
  |
  v
BINANCE AGENT OS
  |
  +-----------------------------+
  |             |               |
  v             v               v
PRICE DATA   POSITIONING     ORDER FLOW
  |             |               |
  |             |               |
  |             |               |
  +-------------+---------------+
                |
                v
        FEATURE EXTRACTION
                |
      +---------+----------+
      |                    |
      v                    v
PRICE / STRUCTURE     LEVERAGE / FLOW
      |                    |
      +---------+----------+
                |
                v
        SQUEEZE ENGINE
                |
       +--------+--------+
       |                 |
       v                 v
SHORT SQUEEZE       LONG SQUEEZE
RISK SCORE          RISK SCORE
       |                 |
       +--------+--------+
                |
                v
          RISK ENGINE
                |
                v
LOW / WATCH / ELEVATED / HIGH / CRITICAL
                |
                v
         🛡️ GUARD VERDICT

---

# 1. User Layer

The user can ask SqueezeGuard questions such as:

`I want to short XYZUSDT. Run SqueezeGuard first.`

or:

`Check BTCUSDT for squeeze risk.`

SqueezeGuard interprets the request and determines whether short-squeeze risk, long-squeeze risk, or both should be evaluated.

---

# 2. Binance Agent OS Layer

SqueezeGuard uses Binance Agent OS as its live market-data layer.

Depending on availability, it retrieves:

- Current Futures price
- 24-hour market statistics
- 5-minute candlesticks
- 15-minute candlesticks
- 1-hour candlesticks
- Funding rate
- Open interest
- Open-interest statistics
- Long/short positioning
- Top-trader positioning
- Taker buy/sell volume
- Futures order book
- Recent market trades
- Data timestamps

SqueezeGuard is designed to operate in market-data-only mode.

It does not require account balances or trade execution.

---

# 3. Feature Extraction Layer

Raw Binance data is transformed into interpretable market features.

Examples:

## Momentum

Determines whether price movement is:

- Weak
- Moderate
- Strong
- Accelerating

## Market Structure

Detects:

- Higher highs
- Higher lows
- Lower highs
- Lower lows
- Support breaks
- Resistance breaks
- Failed breakouts

## Open Interest

Evaluates whether leveraged market participation is:

- Falling
- Stable
- Rising
- Rapidly expanding

## Position Crowding

Analyzes whether positioning appears:

- Balanced
- Long-biased
- Short-biased
- Extremely crowded

## Taker Flow

Measures aggressive market-buy and market-sell activity.

## Order Book

Evaluates visible bid-side and ask-side liquidity.

---

# 4. Squeeze Engine

The Squeeze Engine produces two independent risk assessments:

## Short Squeeze Risk

Looks for conditions where traders holding or entering SHORT positions may become vulnerable to forced exits or aggressive upside movement.

Example combination:

Price rising
+
Open interest rising
+
Short positioning crowded
+
Aggressive taker buying
+
Resistance breakout

---

## Long Squeeze Risk

Looks for conditions where traders holding or entering LONG positions may become vulnerable to forced exits or aggressive downside movement.

Example combination:

Price falling
+
Open interest elevated
+
Long positioning crowded
+
Aggressive taker selling
+
Support breakdown

---

# 5. Scoring Engine

Seven signal groups are evaluated:

| Signal | Maximum |
|---|---:|
| Price Momentum | 15 |
| Open Interest | 20 |
| Funding / Positioning | 15 |
| Long / Short Crowding | 15 |
| Taker Flow | 15 |
| Order Book | 10 |
| Market Structure | 10 |
| TOTAL | 100 |

SqueezeGuard calculates:

SHORT SQUEEZE RISK: 0–100

and

LONG SQUEEZE RISK: 0–100

These are heuristic risk scores, not statistical probabilities.

---

# 6. Counter-Evidence Engine

SqueezeGuard does not only search for evidence supporting its initial hypothesis.

It also searches for evidence against it.

Examples:

- Open interest decreasing
- Taker flow reversing
- Momentum weakening
- Funding normalizing
- Breakout failure
- Major resistance
- Major support
- Order-book imbalance disappearing

This helps reduce confirmation bias.

---

# 7. Risk Classification

SqueezeGuard classifies the final score as:

0–29: LOW

30–49: WATCH

50–69: ELEVATED

70–84: HIGH

85–100: CRITICAL

---

# 8. Guard Verdict

The final output is converted into a simple user-facing warning.

Examples:

🟢 SAFE

🟡 WATCH

🟠 DANGER

🔴 HIGH RISK

🚨 CRITICAL

Example:

`🚨 CRITICAL — Opening a new counter-trend SHORT is currently exposed to elevated squeeze risk.`

The Guard
