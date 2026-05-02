# Source Repository Reference

This file traces all original source repositories that were extracted into
`Metadron_Capital_Prop_Strategies/integrations/`. Use this to check for
upstream updates.

## Repository Map

| Integration Folder | Original Source | GitHub |
|-------------------|----------------|--------|
| `integrations/quant_trading/` | `intelligence_platform/quant-trading` | je-suis-tm/quant-trading |
| `integrations/ai_newton/` | `intelligence_platform/AI-Newton` | AI-Newton |
| `integrations/mirofish/` | `intelligence_platform/MiroFish` | 666ghj/MiroFish |
| `integrations/air_llm/` | `intelligence_platform/Air-LLM` | Air-LLM |
| `integrations/mav_analysis/` | `intelligence_platform/Mav-Analysis` | Mav-Analysis |
| `integrations/stock_chain/` | `intelligence_platform/stock-chain` | stock-chain |
| `integrations/macro_ml/` | `intelligence_platform/ML-Macro-Market` | ML-Macro-Market |
| `integrations/stock_prediction/` | `intelligence_platform/Stock-techincal-prediction-model` | Stock-techincal-prediction-model |
| `integrations/trade_the_event/` | `intelligence_platform/TradeTheEvent` | TradeTheEvent |
| `integrations/frb/` | `intelligence_platform/FRB` | avelkoski/FRB |
| `integrations/hedgefund_tracker/` | `intelligence_platform/hedgefund-tracker` | hedgefund-tracker |
| `integrations/ai_hedgefund/` | `intelligence_platform/ai-hedgefund/src` | ai-hedgefund |
| `integrations/nvidia_gpu/` | `intelligence_platform/nividia-repo` | nividia-repo |
| `integrations/news_engine_nodejs/` | `news-engine/` | newsfilter.io client |
| `integrations/distress/financial_distress_prediction/` | `intelligence_platform/FinancialDistressPrediction` | FinancialDistressPrediction |
| `integrations/distress/financial_distressed_repo/` | `intelligence_platform/financial-distressed-repo` | financial-distressed-repo |
| `integrations/distress/sophisticated_distress/` | `intelligence_platform/sophisticated-distress-analysis` | sophisticated-distress-analysis |
| `plugins/` | `intelligence_platform/plugins` | internal |
| `agent_skills/` | `intelligence_platform/agent_skills` | internal |
| `qstrader/` | `intelligence_platform/qstrader` | mhallsmoore/qstrader |

## Removed (not extracted — reference only)

| Original Source | Reason |
|----------------|--------|
| `intelligence_platform/wondertrader` | C++ source — Python reimplementation in `engine/execution/wondertrader_engine.py` |
| `intelligence_platform/exchange-core` | Java source — Python reimplementation in `engine/execution/exchange_core_engine.py` |
| `intelligence_platform/CTA-code` | Reference textbooks only — never imported |
| `intelligence_platform/Quant-Developers-Resources` | Reference docs only — never imported |
| `intelligence_platform/Stock-prediction` | Jupyter notebooks only — never imported |
| `intelligence_platform/EquityLinkedGICPooling` | README reference only |
| `intelligence_platform/Ruflo-agents` | TypeScript framework — partially referenced |
| `intelligence_platform/get-shit-done` | GSD templates — wired via plugins/ |
| `intelligence_platform/open-bb` | Vendored OpenBB — installed via pip |
| `intelligence_platform/Financial-Data` | Superseded by engine/data/openbb_data.py |
| `intelligence_platform/Kserve` | Full K8s SDK — only integration file was used, removed entirely |

## How to Check for Updates

```bash
# Example: check if quant-trading has new commits
cd /tmp && git clone https://github.com/je-suis-tm/quant-trading.git
diff -r quant-trading/ Metadron_Capital_Prop_Strategies/integrations/quant_trading/
```
