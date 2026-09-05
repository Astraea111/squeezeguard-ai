# 🛡️ SqueezeGuard AI

**Detect the squeeze before the squeeze detects you.**

SqueezeGuard AI is an explainable crypto squeeze-risk intelligence agent powered by Binance Agent OS.

Instead of blindly generating LONG or SHORT signals, SqueezeGuard analyzes live Binance USDⓈ-M Futures market data to identify conditions that may expose traders to:

- SHORT SQUEEZE risk
- LONG SQUEEZE risk

SqueezeGuard is designed as a market-risk intelligence layer before a trader enters a dangerous counter-trend position.

---

# 🚨 The Problem

Crypto traders often make decisions like:

> "This token already pumped 30%. I should short it."

or:

> "This token crashed 20%. I should long the bounce."

But price movement alone does not reveal whether leveraged positioning is becoming unstable.

A market may simultaneously have:

- Rising open interest
- Crowded positioning
- Aggressive taker flow
- Funding imbalance
- Breakout structure
- Order-book pressure

These conditions can create violent squeeze environments.

SqueezeGuard was created to detect that risk before the trader blindly fades the move.

---

# 💡 The Solution

A trader can ask:

`I want to short BTCUSDT. Run SqueezeGuard first.`

SqueezeGuard then uses Binance Agent OS to retrieve current market data and calculate two independent risk scores:

### SHORT SQUEEZE RISK
0–100

### LONG SQUEEZE RISK
0–100

The result includes:

- Score breakdown
- Market snapshot
- Supporting evidence
- Counter-evidence
- Critical market levels
- Guard Verdict

---

# 🔶 Powered by Binance Agent OS

SqueezeGuard uses Binance Agent OS as its live Binance market-data layer.

Depending on availability, the agent analyzes:

- Futures price
- 24H price statistics
- 5m candlesticks
- 15m candlesticks
- 1H candlesticks
- Funding rate
- Open interest
- Open-interest trend
- Long/short ratio
- Top-trader positioning
- Taker buy/sell volume
- Futures order book
- Recent trades
- Data timestamps

SqueezeGuard is designed to operate in market-data-only mode.

No balances are required.

No trades need to be executed.

---

# 🧠 How SqueezeGuard Works

```text
USER
  |
  v
🛡️ SQUEEZEGUARD AI
  |
  v
🔶 BINANCE AGENT OS
  |
  +------------------------------+
  |              |               |
  v              v               v
PRICE DATA   POSITIONING     ORDER FLOW
  |              |               |
  +--------------+---------------+
                 |
                 v
        FEATURE EXTRACTION
                 |
                 v
         SQUEEZE ENGINE
          /           \
         v             v
 SHORT SQUEEZE     LONG SQUEEZE
    SCORE             SCORE
         \             /
          \           /
           v         v
          RISK ENGINE
               |
               v
 LOW / WATCH / ELEVATED / HIGH / CRITICAL
               |
               v
        🛡️ GUARD VERDICT

📊 SqueezeGuard Scoring Model
SqueezeGuard uses seven market-signal categories.
Category
Maximum Points
Price Momentum
15
Open Interest
20
Funding / Positioning
15
Long / Short Crowding
15
Taker Flow
15
Order Book
10
Market Structure
10
TOTAL
100
SqueezeGuard calculates TWO independent scores:
SHORT SQUEEZE RISK: 0–100

LONG SQUEEZE RISK: 0–100
🚦 Risk Levels
Score
Risk Level
0–29
🟢 LOW
30–49
🟡 WATCH
50–69
🟠 ELEVATED
70–84
🔴 HIGH
85–100
🚨 CRITICAL
Important:
The SqueezeGuard Score is a heuristic risk score.
It is NOT a statistical probability.
For example:
85/100
does NOT mean:
85% probability of a squeeze.
It means that multiple squeeze-risk conditions are strongly aligned.
🔍 Short Squeeze Logic
SHORT SQUEEZE RISK increases when multiple bullish squeeze conditions align.
Examples include:
Strong positive price momentum
Higher highs and higher lows
Resistance breakout
Price rising together with open interest
Short-biased positioning
Unusual funding combined with bullish price action
Strong taker-buy dominance
Bid-side pressure
Ask liquidity absorption
Shallow pullbacks
Expanding bullish volatility
SqueezeGuard never declares a short squeeze simply because a token has already increased significantly in price.
Multiple signals must align.
🔻 Long Squeeze Logic
LONG SQUEEZE RISK increases when multiple bearish squeeze conditions align.
Examples include:
Strong negative price momentum
Lower highs and lower lows
Support breakdown
Falling price with elevated or increasing open interest
Long-biased positioning
Unusual funding combined with bearish price action
Strong taker-sell dominance
Ask-side pressure
Bid liquidity absorption
Weak rebounds
Expanding downside volatility
Multiple signals must align before SqueezeGuard issues a high-risk warning.
🔎 Explainable Score Breakdown
SqueezeGuard does not only return a final number.
It shows exactly how the score was constructed.
Example:
SHORT SQUEEZE SCORE BREAKDOWN

Price Momentum:        9/15
Open Interest:         4/20
Funding / Positioning: 5/15
Long / Short Crowding: 5/15
Taker Flow:           11/15
Order Book:            7/10
Market Structure:      7/10

TOTAL:                48/100
RISK: WATCH
The category points must add exactly to the final score.
Each category should be justified using current Binance market evidence.
This makes SqueezeGuard transparent and explainable.
⚖️ Counter-Evidence Engine
SqueezeGuard does not only search for information supporting a squeeze thesis.
It also actively searches for evidence against it.
Examples include:
Open interest decreasing
Momentum weakening
Funding normalizing
Taker flow reversing
Breakout failure
Strong nearby resistance
Strong nearby support
Order-book pressure disappearing
This helps reduce confirmation bias.
A HIGH or CRITICAL score should require several independent categories to align.
🛡️ Guard Verdict
After calculating both scores, SqueezeGuard translates the analysis into a simple risk warning.
Possible Guard Verdicts:
🟢 SAFE

🟡 WATCH

🟠 DANGER

🔴 HIGH RISK

🚨 CRITICAL
Example:
🚨 CRITICAL

Opening a new counter-trend SHORT is currently
exposed to elevated squeeze risk.
The Guard Verdict is a risk warning.
It does not guarantee future market direction.
🧪 Live Binance Agent OS Example
SqueezeGuard V2 was tested using current BTCUSDT USDⓈ-M Futures data retrieved through Binance Agent OS.
Example result:
SHORT SQUEEZE RISK

Price Momentum:        9/15
Open Interest:         4/20
Funding / Positioning: 5/15
Long / Short Crowding: 5/15
Taker Flow:           11/15
Order Book:            7/10
Market Structure:      7/10

TOTAL: 48/100
RISK: WATCH
And:
LONG SQUEEZE RISK

Price Momentum:         5/15
Open Interest:          7/20
Funding / Positioning: 10/15
Long / Short Crowding: 12/15
Taker Flow:             4/15
Order Book:             4/10
Market Structure:       4/10

TOTAL: 46/100
RISK: WATCH
The result was:
SHORT SQUEEZE: 48/100 — WATCH

LONG SQUEEZE: 46/100 — WATCH

GUARD VERDICT:

NEUTRAL / COMPRESSION
This example is important because SqueezeGuard did NOT force a bullish or bearish conclusion.
The system detected vulnerabilities on both sides while also identifying evidence that weakened each squeeze thesis.
See:
EXAMPLE_OUTPUT_V2.md
for the complete live example.
💬 Demo Prompt
A basic SqueezeGuard query can be as simple as:
I am considering SHORTING BTCUSDT.

Run SqueezeGuard first.
For a full analysis:
Using Binance Agent OS, run SqueezeGuard V2 on BTCUSDT USDⓈ-M Futures using CURRENT market data.

Retrieve:

- Current price
- 24H change
- 5m candles
- 15m candles
- 1H candles
- Funding rate
- Open interest
- Open-interest trend
- Long/short positioning
- Top-trader positioning
- Taker buy/sell volume
- Futures order book
- Data timestamps

Calculate BOTH:

SHORT SQUEEZE RISK
LONG SQUEEZE RISK

Use this scoring model:

Price Momentum: 15
Open Interest: 20
Funding / Positioning: 15
Long / Short Crowding: 15
Taker Flow: 15
Order Book: 10
Market Structure: 10

Show the actual point breakdown for every category.

The category points must add exactly to the final score.

Also return:

- Market Snapshot
- Supporting Evidence
- Counter Evidence
- Critical Market Level
- Guard Verdict

The scores are heuristic risk scores, not probabilities.

Market-data only.

Do not access balances.

Do not place, modify, or cancel any transaction.
🔐 Safety by Design
SqueezeGuard is a market-risk intelligence agent.
It does NOT automatically:
Place orders
Modify orders
Cancel orders
Transfer assets
Require account balances
SqueezeGuard is designed to help traders understand leveraged-market risk before acting.
It does not guarantee future price direction.
📁 Repository Structure
squeezeguard-ai/

├── README.md
├── LICENSE
├── SYSTEM_PROMPT.md
├── SCORING.md
├── ARCHITECTURE.md
├── DEMO.md
├── EXAMPLE_OUTPUT.md
└── EXAMPLE_OUTPUT_V2.md
SYSTEM_PROMPT.md
Defines SqueezeGuard behavior, required Binance data, safety rules and output structure.
SCORING.md
Explains the transparent 100-point squeeze-risk scoring engine.
ARCHITECTURE.md
Explains how Binance Agent OS data flows through SqueezeGuard.
DEMO.md
Contains the demo workflow and example prompts.
EXAMPLE_OUTPUT.md
Contains an early live SqueezeGuard test.
EXAMPLE_OUTPUT_V2.md
Contains the explainable V2 live Binance Agent OS test with category-level scoring.
🎯 Core Use Case
SqueezeGuard is designed for situations such as:
Trader:

"This coin has pumped hard.
I want to SHORT it."

        ↓

🛡️ SqueezeGuard:

"Run risk analysis first."

        ↓

🔶 Binance Agent OS

Price
Candles
Funding
Open Interest
Positioning
Taker Flow
Order Book

        ↓

SqueezeGuard Scoring Engine

        ↓

SHORT SQUEEZE RISK
87/100 — CRITICAL

        ↓

🚨 GUARD WARNING

Do not blindly fade the move.
The same concept also applies when a trader considers LONGING a rapidly falling market.
🚀 Future Development
Future versions of SqueezeGuard could include:
Multi-symbol Futures scanning
Automatic squeeze candidate ranking
Squeeze-risk alerts
Historical score tracking
Market-regime detection
Cross-symbol comparison
Visual SqueezeGuard dashboard
Dynamic score calibration
Squeeze-risk monitoring over time
The hackathon version focuses on explainable live risk analysis using Binance Agent OS market data.
🏆 Binance Agent OS Mini Hackathon 2026
SqueezeGuard AI was built for Track A — Build an AI Agent with Agent OS.
The project demonstrates how Binance Agent OS can be used as a live market-intelligence layer for an explainable AI risk agent.
Rather than automatically executing trades, SqueezeGuard transforms Binance Futures market data into actionable risk intelligence.
🛡️ SqueezeGuard AI
Detect the squeeze before the squeeze detects you.
Powered by Binance Agent OS.
Market-risk intelligence, not guaranteed market predictions.
