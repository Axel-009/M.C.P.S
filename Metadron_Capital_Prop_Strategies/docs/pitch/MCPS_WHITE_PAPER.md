# M.C.P.S

## Metadron Capital Prop Strategies

---

### White Paper & Investment Manifesto

---

## I. Firm Overview

Metadron Capital Prop Strategies is a proprietary quantitative investment firm operating a fully autonomous, multi-asset trading platform. The firm deploys systematic strategies across approximately 1,600 securities spanning US equities, listed options, exchange-traded futures, fixed income instruments, and commodity ETFs.

The platform is architected as a single integrated system — from raw market data ingestion through signal generation, machine learning intelligence, risk-adjusted position sizing, and institutional-grade algorithmic execution on Interactive Brokers. Every component operates under a unified wiring specification that enforces correct data flow, eliminates manual intervention, and ensures complete auditability of every signal, decision, and order.

MCPS does not trade on intuition. Every position is the output of a quantifiable process with a documented edge, sized by Kelly criterion, filtered by a four-gate quality standard, and executed via native TWAP/VWAP algorithms. The system operates continuously during market hours with a closed-loop learning mechanism that adapts signal weights, regime priors, and risk thresholds based on realised execution outcomes.

---

## II. Investment Philosophy

### Core Principles

**Fundamentals First.** Forty percent of the decision weight is allocated to fundamental quality assessment — return on invested capital, free cash flow generation, Graham-Dodd valuation metrics, credit quality, and earnings stability. No position is initiated without fundamental conviction, regardless of momentum or sentiment signals.

**Beta Managed, Alpha Extracted.** Portfolio beta is managed within a 7–12% annualised return corridor, aligned with the S&P 500 historical earnings yield range. Alpha is extracted through top-down macro regime classification flowing into bottom-up security selection. The platform targets 95% or greater alpha contribution through aggressive multi-sleeve allocation with continuous walk-forward optimisation.

**Edge-Gated Options.** Options are treated as precision instruments, not speculative tools. Every options position requires a quantifiable mispricing edge of at least 200 basis points between the platform's fair value estimate (computed via Black-Scholes and Monte Carlo simulation) and the observed market price. Positions are sized by Kelly criterion and require a minimum of five contracts. No edge detected means no allocation, regardless of available capital.

**Regime Awareness.** The platform classifies the macro environment into four regimes — Trending, Range, Stress, and Crash — using a ten-layer intelligence tensor that fuses liquidity state, risk state, and capital flow dynamics. Regime classification adjusts leverage caps, beta targets, hedge ratios, and the quality threshold for trade approval.

**Risk Discipline.** A 10% portfolio drawdown triggers an automatic kill switch requiring manual operator reset. Per-position drawdowns exceeding 20% trigger automatic liquidation. Ten pre-trade risk gates must pass before any order reaches the broker. There are no overrides to these constraints.

---

## III. Universe & Asset Coverage

| Asset Class | Scope | Role |
|-------------|-------|------|
| US Equities | S&P 500 + S&P 400 + S&P 600 (~1,500 names) | Core alpha generation |
| UK Equities | FTSE 100 representative ADRs | International diversification |
| Listed Options | Selected securities, edge-gated | Convexity capture + mispricing |
| Exchange Futures | ES, NQ, YM, RTY, VX, ZN, ZB, ZF, ZT | Beta corridor management |
| Fixed Income | G10 + India sovereign, US IG/HY corporate | Macro signal + hedging |
| Commodities | GLD, SLV, USO, UNG, DBA, DBC, COPX, WEAT, CORN | Cyclical pattern signals |
| Currencies | G10 + INR + JPY | Macro regime context |
| Econometrics | 40+ FRED series (GDP, CPI, M2, SOFR, WALCL) | Regime classification |

The universe is scanned continuously during market hours across four sequential runs, with approximately 1,600 securities evaluated per cycle.

---

## IV. Signal Architecture

The platform operates two independent, parallel analytical tracks that converge at a unified intelligence layer. This dual-track design ensures that macro-driven fundamental analysis and news-driven event intelligence operate without cross-contamination.

### Track A — Top-Down Macro to Bottom-Up Fundamental Microstructure

A sequential pipeline that begins at the macro core — tracking money velocity from Federal Reserve balance sheet dynamics — and progressively distils down to individual security microstructure analysis. The flow is explicitly top-down to bottom-up:

1. **Money Velocity Core** — Fisher V=GDP/M2, credit impulse, TED spread, SOFR tracking, Fed reserve distribution. This is the starting point — understanding where liquidity is flowing at the systemic level.

2. **Macro Regime Classification** — The Global Monetary Tension Framework (GMTF) uses SDR-weighted tension with four non-linear gamma multipliers (liquidity, FX shock, wage, reserve) to classify the environment as Trending, Range, Stress, or Crash. This determines the macro lens through which all downstream analysis is conducted.

3. **Sector & Trend Identification** — Once the regime is classified, the MetadronCube intelligence tensor C(t) = f(L, R, F) identifies which sectors and trends are favoured. Capital flow models detect rotation patterns, the yield curve analyser identifies rate-sensitive sectors, and the credit pulse monitor flags credit cycle positioning. This categorical identification determines where to look.

4. **Bottom-Up Fundamental Microstructure** — Only after sectors and trends are identified does the platform drill into individual securities. Graham-Dodd-Klarman security analysis scores each name on ROIC, FCF, margin of safety, normalised earnings, and 8-test investment grading. Cross-asset contagion modelling identifies systemic risk exposure per name. Statistical arbitrage detects relative value mispricing within identified sectors. Distressed asset screening (five-model ensemble) evaluates credit quality at the individual security level.

The key design principle: **the macro regime tells us where to look; the fundamental microstructure analysis tells us what to buy.** No security is evaluated in isolation from its macro context, and no macro signal triggers a trade without bottom-up fundamental confirmation.

### Track B — News-Driven Event Intelligence

An independent pipeline processing real-time news from over 10,000 sources and running agent-based market simulation on flagged securities:

- **Real-Time News Processing** — WebSocket feed with sentiment scoring and urgency categorisation
- **Agent-Based Market Simulation** — Kyle Lambda and Heterogeneous Agent Model simulations per news-flagged ticker
- **Combined Score** — 40% news sentiment + 60% agent simulation direction
- **Event Enrichment** — Signals feed directly into Event-Driven and Contingent Value Rights engines

Both tracks run with zero cross-dependencies and converge at the Alpha Optimiser.

---

## V. Intelligence & Machine Learning

### Alpha Optimiser

All signals from both tracks converge into a dual alpha scoring pipeline:

- **Standard Pipeline** — Gradient boosted models (XGBoost 60% + Linear Regression 40%) with CAPM alpha extraction (20% blend), quality ranking across 22 engineered features, and EWMA covariance estimation
- **Enhanced Pipeline** — Walk-forward validation with a 50+ factor library and sector-level mean-variance optimisation via SLSQP

The optimiser performs universe merge across four scan runs, deduplication by ticker (retaining highest confidence), and allocation cap enforcement before scoring.

### Ten-Tier Machine Learning Ensemble

Every potential trade receives a weighted directional vote from ten independent models:

| Tier | Model | Weight | Focus |
|------|-------|--------|-------|
| T1 | Neural Network | 1.0 | Price direction prediction |
| T2 | Momentum / Mean-Reversion | 1.2 | Technical momentum |
| T3 | Volatility Regime | 0.8 | Vol compression / expansion |
| T4 | Monte Carlo | 0.9 | Probabilistic risk |
| T5 | Fundamental Quality | 1.1 | Graham-Dodd grading |
| T6 | News + Agent Simulation | 1.0 | Real-time sentiment |
| T7 | Distressed Asset | 0.9 | Credit distress detection |
| T8 | Event-Driven | 1.0 | M&A arbitrage, PEAD |
| T9 | Contingent Value Rights | 0.7 | CVR valuation |
| T10 | Credit Quality | 0.9 | Credit scoring (AAA–D) |

The ensemble produces a weighted vote score in [-10, +10] that feeds into the decision layer.

---

## VI. Decision Framework

### Four-Gate Quality Filter

Every trade must pass a cross-asset, asset-agnostic quality filter. All gates apply uniformly to equities, options, futures, and ETFs.

| Gate | Weight | ML Tiers | Function |
|------|--------|----------|----------|
| Fundamentals | 40% | T1, T5, T7, T9, T10 | Quality, ROIC, FCF, credit, earnings + regime quality modifier |
| Flow & Headlines | 20% | T6, T8 | News sentiment, ETF flow, sector rotation |
| Macro Regime | 20% | T3, T4 | Direction alignment, VaR headroom, drawdown |
| Momentum | 20% | T1, T2 | RSI, MACD, breakout, cross-asset momentum |

A minimum composite score of 0.55 is required for trade approval. The Fundamentals gate must pass independently — no trade proceeds without fundamental conviction regardless of composite score.

### Position Sizing

Approved trades are sized via the Kelly criterion with a 1.5x aggressive multiplier, volatility-normalised against a 15% thesis standard, and capped at 20% of NAV per position.

---

## VII. Portfolio Construction

### Allocation Structure

| Sleeve | Target Allocation | Description |
|--------|------------------|-------------|
| Investment Grade Equities | 40% | All market caps, quality names |
| High Yield Equities | 10% | BB-B rated, leveraged opportunities |
| Distressed Equity | 10% | Fallen angels, recovery plays |
| Cashflow ETFs | 15% | Monthly distribution vehicles (DRIP reinvestment) |
| Fixed Income / Macro | 5% | FI signals + macro relative value |
| Event-Driven / CVR | 10% | M&A arbitrage, PEAD, contingent value |
| Options (notional) | 25% | Edge-gated only (≥200bps mispricing) |
| Futures (notional) | 15% | Beta corridor hedging (ES/NQ/VX) |
| Margin | 8% | Initial margin for derivatives overlay |
| Cash Reserve | 2% | Dry powder floor (never breached) |

### Options Discipline

1. Black-Scholes theoretical pricing establishes fair value
2. Monte Carlo simulation (10,000 paths) estimates win probability and expected payoff
3. Fair value versus market price must demonstrate ≥200 basis points of edge
4. Kelly criterion sizes the position based on detected mispricing
5. Minimum five contracts per position — no token allocations
6. No edge detected → no allocation, regardless of available budget

---

## VIII. Execution

### Algorithmic Order Routing

All orders route through a unified L7 Execution Surface — a single mandatory entry point that fuses micro-price estimation, order matching simulation, risk gating, and broker execution into one continuous arm.

| Order Profile | Algorithm | Method |
|--------------|-----------|--------|
| Notional > $50,000 | TWAP | Time-weighted server-side splitting |
| Standard | VWAP | Volume-weighted market participation (≤25%) |
| Medium urgency | Adaptive | Broker selects optimal strategy |
| High urgency / kill switch | Market | Immediate fill |

Execution is routed exclusively through Interactive Brokers via native algo orders (ib_insync SDK). No other broker is used. A trade log records every generated order for reconciliation — providing a complete audit trail of what the platform intended versus what was executed on the broker.

### Execution Quality

- **Micro-price estimation** adjusts limit prices based on order flow imbalance before submission
- **Transaction cost analysis** decomposes every fill into spread, market impact, timing, and commission components
- **Execution learning loop** continuously optimises routing strategy per context bucket (ticker × product × signal × regime × time-of-day × volatility × order size)

---

## IX. Risk Management

### Portfolio-Level Controls

| Control | Threshold | Action |
|---------|-----------|--------|
| Portfolio Drawdown Kill Switch | 10% | Automatic halt, manual operator reset required |
| Per-Position Drawdown | 20% | Automatic liquidation via L7 |
| Daily Loss Circuit Breaker | 3% NAV | All new orders halted |
| Gross Leverage | 250% | Orders exceeding limit rejected |
| Net Leverage | 150% | Orders exceeding limit rejected |
| Trade Throttle | 100 per day | Prevents overtrading |

### Ten Pre-Trade Risk Gates

Every order must pass all ten gates inside the L7 Execution Surface before reaching the broker:

G1 Single position ≤ 10% NAV · G2 Sector concentration ≤ 30% NAV · G3 Daily loss ≤ 3% NAV · G4 Gross leverage ≤ 250% · G5 Net leverage ≤ 150% · G6 Trade throttle ≤ 100/day · G7 Max drawdown ≤ 10% · G8 Cash sufficiency · G9 Options delta ≤ 20% NAV · G10 Futures notional ≤ 50% NAV

### MetadronCube Kill Switch

The MetadronCube intelligence tensor monitors HY OAS spreads, VIX term structure, and market breadth continuously. When conditions trigger — HY OAS +35bp, VIX term flat/inverted, breadth below 50% — the kill switch activates, capping portfolio beta at 0.35 and halting all new position entry.

---

## X. Continuous Learning

The platform operates a closed-loop feedback system with seven independent learning channels:

| Channel | Input | Adjusts | Feeds Back To |
|---------|-------|---------|---------------|
| Signal Accuracy | Trade P&L vs signal prediction | ML ensemble tier weights | Intelligence Layer |
| Execution Quality | Slippage patterns | Routing strategy selection | Execution Layer |
| Regime Feedback | Regime prediction accuracy | HMM transition priors | Signal Layer |
| Alpha Decay | Time-to-alpha-erosion | Position holding period | Intelligence Layer |
| Risk Calibration | Risk event frequency | Gate thresholds | Decision Layer |
| Agent Performance | Individual agent accuracy | Agent promotion / demotion | Intelligence Layer |
| Cross-Asset | Sector allocation effectiveness | Macro sector weights | Signal Layer |

Weight adjustments are damped at ±5% per cycle with a three-reversal oscillation detector to prevent the system from chasing noise.

### Agent Hierarchy

Autonomous sector-specialist agents are ranked and promoted based on sustained performance:

| Rank | Requirements | Autonomy |
|------|-------------|----------|
| Director | Sharpe > 2.5, accuracy > 85% | Full autonomy |
| General | Sharpe > 2.0, accuracy > 80% | High autonomy |
| Captain | Sharpe > 1.5, accuracy > 55% | Standard |
| Lieutenant | Sharpe > 1.0, accuracy > 50% | Restricted sizing |
| Recruit | Below thresholds | Under review |

---

## XI. Technology Infrastructure

| Component | Implementation |
|-----------|---------------|
| Core Engine | Python (pure-numpy fallbacks, no single-framework dependency) |
| ML Models | XGBoost, scikit-learn, HMM (hmmlearn), pure-numpy PPO |
| Data Source | Interactive Brokers (real-time) + OpenBB (historical, 34+ providers) |
| Execution | Interactive Brokers (TWS/Gateway via ib_insync, native TWAP/VWAP) |
| Options Pricing | Black-Scholes + Monte Carlo (10,000 path simulation) |
| Monitoring | Prometheus + Grafana (17 real-time L7 metrics) |
| Process Management | PM2 (17 services, 24/7 continuous operation) |
| Deployment | Dedicated server (Hetzner GEX44) + Cloudflare SSL |
| CI/CD | GitHub Actions (wiring validation, engine tests, stale reference checks) |

The system is designed with graceful degradation — every external dependency is wrapped in fault-tolerant imports. If any component fails, the platform continues operating with reduced capability rather than halting entirely. A machine-readable wiring manifest validates all 43 components, 59 data flow edges, and 10 routing rules on every deployment.

---

## XII. Observability & Auditability

- **17 real-time Prometheus metrics** — NAV, leverage, risk level, kill switch status, slippage, fill latency, TWAP/VWAP order counts, TCA cost decomposition
- **Anomaly detection** across 8 dimensions — z-score, volume, correlation, VIX, credit, breadth
- **Trade log reconciliation** — every generated order logged with timestamp, comparing platform intent versus broker execution
- **Hourly CSV snapshots** of portfolio state for audit trail
- **Grafana dashboards** — engines, trading, GPU, PM2, system health (5 dashboards, Contabo-hosted)

---

## XIII. Competitive Differentiation

**1. Fundamentals-First Architecture.** Unlike momentum-driven systematic funds, MCPS places 40% of decision weight on fundamental quality. This prevents the system from chasing price action without underlying value and provides natural drawdown protection during regime transitions.

**2. Edge-Gated Derivatives.** Options positions are only initiated when quantitative mispricing is detected and confirmed by two independent pricing models. This eliminates the common systematic fund practice of deploying options budget mechanically regardless of relative value.

**3. Independent Parallel Signal Tracks.** Macro-driven and news-driven analysis run with zero cross-dependencies, preventing one track's noise from contaminating the other. Both converge only at the intelligence layer where they are weighted independently.

**4. Institutional Execution Quality.** Native IBKR TWAP/VWAP algorithms with micro-price estimation, continuous execution learning, and full transaction cost analysis — capabilities typically reserved for institutional desks.

**5. Closed-Loop Adaptation.** Every execution outcome feeds back into signal weights through seven independent channels with damped updates, ensuring the system adapts to changing market conditions without manual recalibration or overfitting to recent data.

**6. Complete Auditability.** Every signal, decision, order, and fill is logged with timestamps. The reconciliation engine provides complete transparency into what the system intended versus what was executed — a level of audit trail that exceeds most institutional requirements.

---

## XIV. Operational Structure

### Deployment Architecture

```
Hetzner GEX44 (Dedicated Server)
├── Engine API (port 8001)
├── Express Frontend (port 5000)
├── LLM Inference Bridge (port 8002)
├── Model Servers (ports 8003-8006)
├── Live Loop Orchestrator (continuous)
├── Learning Loop (continuous)
└── PM2 Process Manager (17 services)

Contabo VPS (Monitoring)
├── Prometheus (port 9090)
├── Grafana (port 3000)
├── Alertmanager
└── WireGuard tunnel to Hetzner

Cloudflare (SSL/CDN)
└── Domain → Nginx reverse proxy → services
```

### Live Operation Schedule

| Time (ET) | Mode | Activity |
|-----------|------|----------|
| 08:00–09:30 | Pre-market | Full data refresh, overnight signals, SEC scan |
| 09:30 | Market open | Full pipeline execution, first trades |
| 09:30–16:00 | Intraday | 1-minute heartbeat, all 7 phases active |
| 16:00 | Market close | Reconciliation, learning snapshot, scorecard |
| 16:00–20:00 | After-hours | Earnings scan, reduced frequency |
| 20:00–08:00 | Overnight | Backtesting, ML retraining, pattern evolution |

---

*M.C.P.S — Metadron Capital Prop Strategies*

*Systematic Alpha Through Intelligent Automation*

---

**Confidential.** This document is provided for informational purposes only and does not constitute an offer to sell or a solicitation of an offer to buy any securities. Past performance is not indicative of future results. All trading involves risk of loss.
