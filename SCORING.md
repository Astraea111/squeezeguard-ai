# 🛡️ SqueezeGuard Scoring Engine

SqueezeGuard uses a transparent heuristic scoring system to estimate
SHORT SQUEEZE RISK and LONG SQUEEZE RISK.

The score ranges from 0 to 100.

The score is NOT a statistical probability.

For example:

85/100 means that multiple squeeze-risk conditions are strongly aligned.

It does NOT mean there is an 85% probability that a squeeze will occur.

---

# Risk Levels

| Score | Risk Level |
|------|------------|
| 0–29 | LOW |
| 30–49 | WATCH |
| 50–69 | ELEVATED |
| 70–84 | HIGH |
| 85–100 | CRITICAL |

---

# Total Score

SqueezeGuard evaluates seven groups of market signals.

| Factor | Maximum Points |
|------|------:|
| Price Momentum | 15 |
| Open Interest | 20 |
| Funding / Positioning | 15 |
| Long / Short Crowding | 15 |
| Taker Flow | 15 |
| Order Book | 10 |
| Market Structure | 10 |
| TOTAL | 100 |

---

# 1. Price Momentum — Maximum 15 Points

SqueezeGuard evaluates recent 5m, 15m and 1H price action.

## Short Squeeze Risk

0 points:
Weak or bearish momentum.

5 points:
Moderate bullish momentum.

10 points:
Strong bullish momentum across multiple timeframes.

15 points:
Rapid bullish acceleration or parabolic expansion.

## Long Squeeze Risk

The same logic is applied in the opposite direction.

Strong bearish acceleration increases Long Squeeze Risk.

---

# 2. Open Interest — Maximum 20 Points

Open Interest is one of the most important SqueezeGuard signals.

## Short Squeeze Risk

0 points:
Open interest is falling significantly.

5 points:
Open interest is stable.

10 points:
Open interest is moderately increasing.

15 points:
Price and open interest are both rising strongly.

20 points:
Rapid price expansion occurs together with aggressive open-interest growth.

The combination:

Price UP
+
Open Interest UP

may indicate that new leveraged positions are entering the market.

SqueezeGuard does not assume that rising open interest alone is bullish.

It must be evaluated together with price, positioning and order flow.

## Long Squeeze Risk

The opposite condition is evaluated.

Falling price together with elevated or rapidly increasing open interest
can increase Long Squeeze Risk.

---

# 3. Funding and Positioning — Maximum 15 Points

Funding is never used as a standalone squeeze signal.

SqueezeGuard evaluates funding together with price behavior,
open interest and trader positioning.

## Short Squeeze Risk Example

Negative or unusually bearish funding
+
price rising
+
open interest rising

can indicate that bearish positioning is being challenged.

Possible score:

0–5:
Neutral conditions.

5–10:
Moderate positioning imbalance.

10–15:
Strong positioning imbalance aligned with squeeze conditions.

## Long Squeeze Risk

The opposite logic applies.

Highly bullish positioning combined with weakening price action
may increase Long Squeeze Risk.

---

# 4. Long / Short Crowding — Maximum 15 Points

SqueezeGuard analyzes available long/short positioning data.

## Short Squeeze Risk

0 points:
Balanced positioning.

5 points:
Moderate short bias.

10 points:
Heavy short bias.

15 points:
Extreme short crowding while price moves upward.

## Long Squeeze Risk

0 points:
Balanced positioning.

5 points:
Moderate long bias.

10 points:
Heavy long bias.

15 points:
Extreme long crowding while price moves downward.

Crowding alone does not confirm a squeeze.

---

# 5. Taker Buy / Sell Flow — Maximum 15 Points

SqueezeGuard evaluates aggressive market buying and selling.

A simple flow ratio can be interpreted as:

Taker Buy Volume
divided by
Taker Buy Volume + Taker Sell Volume

## Short Squeeze Risk

Around 50%:
Neutral flow.

55–60%:
Moderate buyer dominance.

60–70%:
Strong buyer dominance.

Above 70%:
Extreme aggressive buying.

Possible score:

0 points:
Sellers dominate.

5 points:
Slight buyer dominance.

10 points:
Strong buyer dominance.

15 points:
Extreme aggressive buying aligned with bullish price action.

## Long Squeeze Risk

The same logic is reversed for aggressive selling.

---

# 6. Order Book Imbalance — Maximum 10 Points

SqueezeGuard analyzes Binance Futures order-book depth.

It compares visible bid-side and ask-side liquidity.

## Short Squeeze Risk

0 points:
Ask liquidity dominates.

3 points:
Balanced order book.

5 points:
Moderate bid-side dominance.

8 points:
Strong bid-side dominance.

10 points:
Strong buy-side pressure combined with ask absorption.

## Long Squeeze Risk

The opposite logic applies.

Important:

Order-book liquidity can change rapidly.

Therefore, order-book imbalance is never treated as proof that price
must move in one direction.

---

# 7. Market Structure — Maximum 10 Points

SqueezeGuard evaluates structure using recent candles.

## Short Squeeze Risk

Possible bullish squeeze evidence:

- Higher highs
- Higher lows
- Resistance breakout
- Strong candle closes
- Expanding bullish volume
- Shallow pullbacks
- Failed bearish reversals

Scoring:

0 points:
Bearish structure.

3 points:
Neutral structure.

5 points:
Early bullish structure.

8 points:
Confirmed bullish breakout structure.

10 points:
Strong breakout with continuation characteristics.

## Long Squeeze Risk

The opposite structure is evaluated:

- Lower highs
- Lower lows
- Support breakdown
- Strong bearish closes
- Expanding bearish volume
- Weak rebounds

---

# Multi-Signal Requirement

SqueezeGuard must never declare HIGH or CRITICAL squeeze risk
using only one indicator.

High-confidence alerts require multiple independent categories
to align.

Example:

Price Momentum ↑
+
Open Interest ↑
+
Short Crowding ↑
+
Taker Buying ↑
+
Resistance Breakout

This combination represents a stronger Short Squeeze Risk signal
than any individual metric.

---

# Counter-Evidence Rule

SqueezeGuard must actively search for evidence that contradicts
its primary squeeze thesis.

Examples:

- Momentum weakening
- Open interest falling
- Funding normalizing
- Large resistance nearby
- Taker flow reversing
- Order-book pressure disappearing
- Breakout failure

This reduces confirmation bias.

---

# Final Classification

SqueezeGuard produces TWO independent scores:

SHORT SQUEEZE RISK: XX/100

LONG SQUEEZE RISK: XX/100

The higher score determines the dominant squeeze-risk environment.

However, SqueezeGuard must still explain both sides.

---

# Safety Principle

SqueezeGuard is a market-risk intelligence system.

It does not guarantee market direction.

It does not automatically execute trades.

It does not place, modify or cancel orders.

It uses Binance market data to help identify dangerous leveraged market conditions.
