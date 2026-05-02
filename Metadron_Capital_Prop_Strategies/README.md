# M.C.P.S

## Metadron Capital Prop Strategies

Systematic multi-asset investment platform. Fully autonomous signal-to-trade execution across ~1,600 securities.

---

### How It Works

The platform operates two independent parallel signal tracks that converge at a unified intelligence layer:

**Track A — Top-Down Macro to Bottom-Up Fundamentals**

Starts at the macro core — tracking money velocity from Federal Reserve balance sheet dynamics (V=GDP/M2, credit impulse, SOFR, reserves) — then distils through macro regime classification (GMTF: Trending / Range / Stress / Crash) to identify favoured sectors and trends. Only after sectors and trends are categorically identified does the platform drill into individual security microstructure: Graham-Dodd-Klarman fundamental analysis (ROIC, FCF, margin of safety, 8-test investment grading), cross-asset contagion modelling, statistical arbitrage, and distressed asset screening. The macro regime tells us where to look; the fundamental microstructure tells us what to buy.

**Track B — News-Driven Event Intelligence**

Independent from Track A. Processes real-time news from 10,000+ sources (newsfilter.io), runs agent-based market simulation (Kyle Lambda, HAM) on flagged tickers, and produces a combined score (40% sentiment + 60% agent sim) that enriches the Event-Driven and CVR engines.

Both tracks converge at the AlphaOptimizer where signals are scored, deduplicated, and cap-enforced before passing through a 4-gate quality filter (Fundamentals 40%, Flow 20%, Macro 20%, Momentum 20%) and executing via IBKR native TWAP/VWAP algorithms.

---

### Quick Start

```bash
cd Metadron_Capital_Prop_Strategies/
pip install -r requirements.txt
python3 -m engine.wiring_manifest    # validate 43 components, 59 edges, 49 checks
```

### Run Live

```bash
export IBKR_HOST=127.0.0.1
export IBKR_PORT=7497                # 7497=paper, 7496=live
export OPENBB_TOKEN=your_token
export FMP_API_KEY=your_key

python3 scripts/run_open.py          # full pipeline
# or
./scripts/pm2-start.sh --full       # all 17 PM2 services
```

### Test (engine only, no frontend/monitoring)

Follow `docs/architecture/LIVE_SIM_TEST_PROMPT.md` — step-by-step instructions for testing the complete data-to-trade flow without infrastructure.

---

### Structure

```
Metadron_Capital_Prop_Strategies/
├── engine/           — 43 components: signals, intelligence, execution (IBKR)
├── integrations/     — 15 wired repos (quant strategies, AI-Newton, MiroFish, etc.)
├── qstrader/         — Backtesting library
├── plugins/          — GSD/Paul learning plugins
├── agent_skills/     — Claude Skills API
├── frontend/         — React client + Express server + nginx config
├── models/           — Qwen 2.5-7B
├── monitoring/       — Prometheus + Grafana configs
├── tests/            — 106 engine tests
├── scripts/          — run_open, run_close, PM2 launcher, setup
├── config/           — PM2 ecosystem, .env template
├── docs/
│   ├── architecture/ — Architecture DNA, Data Flow Chart, Wiring Manifest
│   ├── deployment/   — Hetzner + Contabo guides (8 steps)
│   ├── pitch/        — White paper, LP overview, slides
│   └── reference/    — WonderTrader, ExchangeCore docs
├── core/             — Platform orchestrator
├── governance/       — Credit classification
└── data/             — Runtime directories
```

### Key Parameters

| Parameter | Value |
|-----------|-------|
| Kill switch | 10% portfolio drawdown |
| Kelly multiplier | 1.5x |
| Options edge gate | ≥200bps mispricing |
| Options min contracts | 5 |
| Decision composite | ≥0.55 |
| Fundamentals gate weight | 40% |
| Gross exposure limit | 250% |
| Net exposure limit | 150% |
| Broker | IBKR (sole, TWAP/VWAP native) |
| LLM | OpenRouter |

---

*Systematic Alpha Through Intelligent Automation*
