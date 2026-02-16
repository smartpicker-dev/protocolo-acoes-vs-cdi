# figures_manifest_v13b1.md

**Fonte (obrigatória em todas as figuras):** “Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS”.

## Snapshots — datas finais efetivas

- **D0:** 2026-02-10
- **D-6m:** 2025-08-08
- **D-12m:** 2025-02-10

**Nota:** D-6m usa **08/08/2025** (último pregão anterior ao alvo 10/08/2025).


## Inputs (CSV v13b1)

- `outputs/metrics/v13b1/T1_total_return_CAGR_v13b1.csv`  
  - SHA256: `a6adee9e7e3e9de3bb39b25f75f10bb7082c498a19a9b2c37fe1077e0c496d80`  
  - Colunas: bundle_version, cut, window, series, series_label, start_date, end_date, total_return, cagr, years, pdf_md5, report_id
- `outputs/metrics/v13b1/T2_risk_core_v13b1.csv`  
  - SHA256: `c05f399282fc83ce59212625f149d86805d8856a6d88edbea8d6d1ff1696cbdb`  
  - Colunas: bundle_version, cut, window, series, series_label, vol_ann, sharpe_excess_cdi, sortino_excess_cdi, max_drawdown, pct_neg_months, worst_month, best_month, N_months, report_id
- `outputs/robustness/v13b1/T3_robust_total_return_CAGR_v13b1.csv`  
  - SHA256: `9e29934c2e71cc5ff265a1fdddfc84aaad70498bd5b93431e79039c06eb83ad5`  
  - Colunas: window, series, start_date_D0, end_date_D0, start_date_D6M, end_date_D6M, start_date_D12M, end_date_D12M, total_return_%_D0, total_return_%_D6M, total_return_%_D12M, total_return_range_pp, total_return_delta_D0_minus_D6M_pp, total_return_delta_D0_minus_D12M_pp, cagr_%_D0, cagr_%_D6M, cagr_%_D12M, cagr_range_pp, cagr_delta_D0_minus_D6M_pp, cagr_delta_D0_minus_D12M_pp, rank_total_return_D0, rank_total_return_D6M, rank_total_return_D12M, rank_cagr_D0, rank_cagr_D6M, rank_cagr_D12M
- `outputs/robustness/v13b1/T3_robust_risk_core_v13b1.csv`  
  - SHA256: `9d9c376ac2af1ee2e2d28a485b142b2960ddc197822cb372660c9bf573912639`  
  - Colunas: window, series, start_date_D0, end_date_D0, start_date_D6M, end_date_D6M, start_date_D12M, end_date_D12M, vol_ann_%_D0, vol_ann_%_D6M, vol_ann_%_D12M, vol_ann_%_range, vol_ann_%_delta_D0_minus_D6M, vol_ann_%_delta_D0_minus_D12M, max_drawdown_%_D0, max_drawdown_%_D6M, max_drawdown_%_D12M, max_drawdown_%_range, max_drawdown_%_delta_D0_minus_D6M, max_drawdown_%_delta_D0_minus_D12M, pct_neg_months_%_D0, pct_neg_months_%_D6M, pct_neg_months_%_D12M, pct_neg_months_%_range, pct_neg_months_%_delta_D0_minus_D6M, pct_neg_months_%_delta_D0_minus_D12M, worst_month_%_D0, worst_month_%_D6M, worst_month_%_D12M, worst_month_%_range, worst_month_%_delta_D0_minus_D6M, worst_month_%_delta_D0_minus_D12M, sharpe_excess_cdi_D0, sharpe_excess_cdi_D6M, sharpe_excess_cdi_D12M, sharpe_excess_cdi_range, sharpe_excess_cdi_delta_D0_minus_D6M, sharpe_excess_cdi_delta_D0_minus_D12M, sortino_excess_cdi_D0, sortino_excess_cdi_D6M, sortino_excess_cdi_D12M, sortino_excess_cdi_range, sortino_excess_cdi_delta_D0_minus_D6M, sortino_excess_cdi_delta_D0_minus_D12M
- `outputs/robustness/v13b1/T3_robust_portfolio_ranking_v13b1.csv`  
  - SHA256: `455c327d05852be893ce59f5ae2e61ea2bd1de9174b980e957568fb60068bb52`  
  - Colunas: window, series, start_date_D0, end_date_D0, start_date_D6M, end_date_D6M, start_date_D12M, end_date_D12M, rank_cagr_D0, rank_cagr_D12M, rank_cagr_D6M, rank_total_return_D0, rank_total_return_D12M, rank_total_return_D6M

## Outputs (figuras)

### F1_total_return_endpoints_v13b1

- Arquivos: `F1_total_return_endpoints_v13b1.png`, `F1_total_return_endpoints_v13b1.pdf`, `F1_total_return_endpoints_v13b1.svg`
- Inputs: `outputs/metrics/v13b1/T1_total_return_CAGR_v13b1.csv`
- Snapshots: D0, D-6m, D-12m (no mesmo gráfico; separados no eixo X)
- Janelas: 5/10/15/20/25 anos
- Notas: Barras mostram **valor final de R$1 (×) = 1 + total_return**; eixo Y em **escala log** para legibilidade. Legenda fixa por série.

### F2_CAGR_bars_v13b1

- Arquivos: `F2_CAGR_bars_v13b1.png`, `F2_CAGR_bars_v13b1.pdf`, `F2_CAGR_bars_v13b1.svg`
- Inputs: `outputs/metrics/v13b1/T1_total_return_CAGR_v13b1.csv`
- Snapshots: D0, D-6m, D-12m (no mesmo gráfico; separados no eixo X)
- Janelas: 5/10/15/20/25 anos
- Notas: CAGR em % a.a. (linear). Mesma ordem de séries e layout da F1.

### F3a_vol_ann_v13b1

- Arquivos: `F3a_vol_ann_v13b1.png`, `F3a_vol_ann_v13b1.pdf`, `F3a_vol_ann_v13b1.svg`
- Inputs: `outputs/metrics/v13b1/T2_risk_core_v13b1.csv`
- Snapshots: D0, D-6m, D-12m (no mesmo gráfico; separados no eixo X)
- Janelas: 5/10/15/20/25 anos
- Notas: Volatilidade anualizada (% a.a.), linear.

### F3b_max_drawdown_v13b1

- Arquivos: `F3b_max_drawdown_v13b1.png`, `F3b_max_drawdown_v13b1.pdf`, `F3b_max_drawdown_v13b1.svg`
- Inputs: `outputs/metrics/v13b1/T2_risk_core_v13b1.csv`
- Snapshots: D0, D-6m, D-12m (no mesmo gráfico; separados no eixo X)
- Janelas: 5/10/15/20/25 anos
- Notas: Máximo drawdown (%). Valores negativos (queda) plotados abaixo de zero.

### F4_robustness_range_v13b1

- Arquivos: `F4_robustness_range_v13b1.png`, `F4_robustness_range_v13b1.pdf`, `F4_robustness_range_v13b1.svg`
- Inputs: `outputs/robustness/v13b1/T3_robust_total_return_CAGR_v13b1.csv`, `outputs/metrics/v13b1/T1_total_return_CAGR_v13b1.csv`
- Snapshots: D0, D-6m, D-12m (range max–min)
- Janelas: 5/10/15/20/25 anos
- Notas: Range (p.p.) do **excesso de CAGR vs CDI** para Portfólios A/B/C.


## Hashes (outputs)

- `F1_total_return_endpoints_v13b1.pdf` — SHA256: `3e7d78bfb59c00985c7fcf8747263b422b75aac48e448e13ff3e43ca18bad176`
- `F1_total_return_endpoints_v13b1.png` — SHA256: `c8c2ff0dad2fc3226bd9dd8d3b58af18242319a026fa3f10903f2b194b3a6422`
- `F1_total_return_endpoints_v13b1.svg` — SHA256: `6d8b24cd248d097ea89ab6464063cba6ea42a7fca6aff9121897d3df2f89f91c`
- `F2_CAGR_bars_v13b1.pdf` — SHA256: `f8a8e03589f157d013369f2c4d7c46d7c8609adb1a3b825cb54e6f33555872c7`
- `F2_CAGR_bars_v13b1.png` — SHA256: `e3afec98361bc9a0dcd796d75670380140bf454204685bd7289dc86c62418197`
- `F2_CAGR_bars_v13b1.svg` — SHA256: `cdf50c5bce077499f276a630106ea31cc07a084c48686556515509f8747156ba`
- `F3a_vol_ann_v13b1.pdf` — SHA256: `2c4872c29f4b8e290d072485fc44933b7d922e5a3d221d2df31b469c36fe5169`
- `F3a_vol_ann_v13b1.png` — SHA256: `fcce7164e293a9540b46e4db7078881774a4c7ebea2a00df44a0d5b371ac7ad4`
- `F3a_vol_ann_v13b1.svg` — SHA256: `d01b38321cbc27810a280be0f7e4208ebf10701a6f31497ba9d1e67a901acc14`
- `F3b_max_drawdown_v13b1.pdf` — SHA256: `3f7a9694c024913232c32789ff984e6f7f4f719e7ed50912c8017a93e20bb823`
- `F3b_max_drawdown_v13b1.png` — SHA256: `6a7b1d6900faabf1d489c09a97dff1bc1d010a4535231227b2812e8cddd6351b`
- `F3b_max_drawdown_v13b1.svg` — SHA256: `40b58804509ab80bd1769beaebd245792b1063e8df70c7a3b38b7409f8497576`
- `F4_robustness_range_v13b1.pdf` — SHA256: `fda81decba86c64c09a5442ec1c1dfcacbc85129af814455222496407d24e813`
- `F4_robustness_range_v13b1.png` — SHA256: `6945a13791f8a46347915cc81ad2dd049d3b678f3e641272eb2184198f103a9a`
- `F4_robustness_range_v13b1.svg` — SHA256: `86977b6fa65c6af990f96113655ce7f776ce82dc4690aeabba5ccdd60ebec6ea`

## Parâmetros visuais (fixos)

- Tamanho: 10 × 4.2 inches; PNG 300 dpi; export também em PDF e SVG.
- Fonte: DejaVu Sans (matplotlib default).
- Legenda: canto superior esquerdo; mesma ordem de séries em todas as figuras.
- Rodapé: Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS
