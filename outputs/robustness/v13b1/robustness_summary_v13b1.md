# Robustez temporal — v13b1 (Agente 06)

**Fonte dos dados:** “Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS”.

## Snapshots (datas finais efetivas)
- **D0:** 10/02/2026  
- **D-12m:** 10/02/2025  
- **D-6m (alvo 10/08/2025):** **08/08/2025** (último dia anterior disponível)

## T3 (robustez): outputs
- `T3_robust_total_return_CAGR_v13b1.csv`
- `T3_robust_risk_core_v13b1.csv`
- `T3_robust_portfolio_ranking_v13b1.csv`

## Quanto muda (principal): excesso de CAGR vs CDI — range (p.p.) entre D0 / D-6m / D-12m
| Janela | PA | PB | PC |
|---|---|---|---|
| 5Y | 4.71 | 9.53 | 4.56 |
| 10Y | 8.36 | 7.61 | 7.97 |
| 15Y | 1.53 | 2.64 | 0.88 |
| 20Y | 0.69 | 0.72 | 0.81 |
| 25Y | 0.32 | 0.90 | 0.49 |

### Bate CDI em todos os snapshots? (excesso de CAGR > 0 em D0, D-6m e D-12m)
| Janela | PA | PB | PC |
|---|---|---|---|
| 5Y | ✅ | ❌ | ✅ |
| 10Y | ✅ | ✅ | ✅ |
| 15Y | ✅ | ✅ | ✅ |
| 20Y | ✅ | ✅ | ✅ |
| 25Y | ✅ | ✅ | ✅ |

**Leitura:** as janelas **5Y e 10Y** exibem a maior sensibilidade ao “dia escolhido”; em **20Y e 25Y** os ranges são menores.

## Estabilidade de ranking (A/B/C) por CAGR
- **10Y**: ordem A/B/C por CAGR = D0 ('PB', 'PC', 'PA'), D-6m ('PB', 'PC', 'PA'), D-12m ('PB', 'PC', 'PA') → **estável**
- **15Y**: ordem A/B/C por CAGR = D0 ('PB', 'PA', 'PC'), D-6m ('PB', 'PC', 'PA'), D-12m ('PC', 'PB', 'PA') → **muda**
- **20Y**: ordem A/B/C por CAGR = D0 ('PB', 'PC', 'PA'), D-6m ('PB', 'PC', 'PA'), D-12m ('PB', 'PC', 'PA') → **estável**
- **25Y**: ordem A/B/C por CAGR = D0 ('PC', 'PA', 'PB'), D-6m ('PA', 'PC', 'PB'), D-12m ('PC', 'PA', 'PB') → **muda**
- **5Y**: ordem A/B/C por CAGR = D0 ('PB', 'PC', 'PA'), D-6m ('PC', 'PA', 'PB'), D-12m ('PC', 'PA', 'PB') → **muda**

## Nota metodológica (core set)
- `total_return_%` e `cagr_%` vêm do snapshot (IND) por janela e série.
- `vol_ann_%`, `sharpe_excess_cdi` e `sortino_excess_cdi` são derivados de retornos mensais (MONTHLY_LONG), conforme Gate02_QA_Report_v13b.md.
