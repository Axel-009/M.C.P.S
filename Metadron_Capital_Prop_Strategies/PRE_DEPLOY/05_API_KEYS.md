# Step 5 — API Keys & Vault Configuration

## 5.1 Using the VAULT Tab

Once the platform is running, open the terminal:
```
https://metadroncapital.com/terminal/#/vault
```

The VAULT tab shows all 8 API key slots. You can set keys directly
from the browser — they deploy immediately to the engines, no restart needed.

## 5.2 Required API Keys

### IBKR (Trade Execution) — REQUIRED

1. Run TWS or IB Gateway (paper or live) on the Hetzner host (or via WireGuard)
2. Set the following in `.env`:

- `IBKR_HOST` → host running TWS/Gateway (default `127.0.0.1`)
- `IBKR_PORT` → `7497` for paper, `7496` for live
- `IBKR_CLIENT_ID` → integer (default `1`)
- `IBKR_PAPER` → `True` for paper, `False` for live

**WARNING**: Setting `IBKR_PAPER=False` and pointing at the live port means REAL MONEY. Be certain.


### FMP (Market Data) — REQUIRED

1. Go to https://site.financialmodelingprep.com/developer/docs
2. Sign up for a free or paid plan
3. Copy your API key from the dashboard

In the VAULT tab, set:
- `FMP_API_KEY` → paste your FMP API key

This is the primary data source for the entire platform (prices, fundamentals, news).

### Xiaomi Mimo V2 Pro (Brain Power LLM) — RECOMMENDED

This powers the Brain Power orchestrator that synthesizes outputs from
all AI models. Without it, Brain Power runs in stub mode (platform still
works, but LLM synthesis is placeholder text).

In the VAULT tab, set:
- `XIAOMI_MIMO_API_KEY` → paste your Xiaomi Mimo API key

### Zep (Agent Simulation Memory) — OPTIONAL

Used by MiroFish agent simulation for knowledge graph memory.
Platform works without it.

In the VAULT tab, set:
- `ZEP_API_KEY` → paste your Zep API key

### OpenBB Token — OPTIONAL

Unlocks additional OpenBB data providers beyond FMP.
Platform works without it (FMP is the primary provider).

In the VAULT tab, set:
- `OPENBB_TOKEN` → paste your OpenBB platform token

## 5.3 Internal Proxy Token

The `METADRON_INTERNAL_TOKEN` is **auto-generated** on first boot.
You don't need to set it. It's used internally for frontend → backend
authentication. You'll see it in the VAULT tab as "auto".

## 5.4 Verify API Keys

In the VAULT tab:
1. Click **TEST** next to each key you've set
2. FMP should show "valid" (it tests a live API call)
3. IBKR should show "valid" (it tests account access)
4. Xiaomi will show "configured" (no live test available)

## 5.5 Alternative: Set Keys via .env

If you prefer not to use the VAULT tab, set keys in `.env.production`:

```bash
nano /opt/metadron/.env.production

# Add your keys:
IBKR_HOST=127.0.0.1
IBKR_PORT=7497
IBKR_CLIENT_ID=1
IBKR_PAPER=True
FMP_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
XIAOMI_MIMO_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxx
```

Then restart PM2:
```bash
pm2 restart all
```

The VAULT will detect these from the environment on next boot.

## 5.6 Claude Code + Jarvis Setup

These are development tools for managing the platform:

```bash
# Claude Code (already installed in Step 2.12)
# Verify it's available:
claude --version

# Jarvis
jarvis --version

# Both use Anthropic API — set your key if not already:
export ANTHROPIC_API_KEY=your_anthropic_key
```

Add to your shell profile for persistence:
```bash
echo 'export ANTHROPIC_API_KEY=your_anthropic_key' >> ~/.bashrc
source ~/.bashrc
```
