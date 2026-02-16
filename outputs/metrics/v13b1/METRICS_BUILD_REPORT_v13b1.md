# Metrics Build Report — v13b1

**Fonte (citar):** Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS.

## Inputs usados (somente congelados)
- estudo_base_dados_master_v3.12_protocol_v13b.xlsx (bundle v13b1)
  - MONTHLY_LONG (retornos mensais + index base 100)
  - RAW_METRICS (total_return/cagr canônicos do PDF + start/end + md5)

## Outputs gerados
- OFFICIAL_METRICS_v13b1.csv
- OFFICIAL_METRICS_v13b1.xlsx
- METRICS_DICTIONARY_v13b1.md
- RECOMPUTE_DIFFS_v13b1.csv

## Checks (consistência)
- vol_ann / worst_month / best_month / pct_neg_months / max_drawdown / sharpe / sortino: recomputados a partir de MONTHLY_LONG e conferidos vs RAW_METRICS (diferenças ~0 por arredondamento numérico).
- total_return e cagr: tratados como canônicos do PDF (RAW_METRICS). 
  - Diferença entre total_return(PDF) e index_final/100-1 monitorada em `total_return_abs_diff`.
  - Resumo por cut×window em `RECOMPUTE_DIFFS_v13b1.csv`.

## Nota
Este build não depende de versões anteriores (v13/v13a/v13b). Apenas v13b1.
