# Gate 02 — Auditoria e Validação (QA)

**Estudo:** Ações vs CDI  
**Bundle auditado:** gate02_bundle_v13b.zip  
**Seed amostragem PDF→Planilha:** 20260214  
**Data do gate:** 14/02/2026

## Resumo executivo

✅ **PASS — OK para liberar análise**

- **QA mecânico (100% da base):** PASS (sem flags críticos).
- **Auditoria amostral PDF→Planilha:** 100% PASS (30/30) dentro das tolerâncias.
- **Validação cruzada externa (sanity check):** CDI verificado em meses cheios via Ipeadata (conforme nota).

### Pontos a corrigir (não bloqueantes)

- **P2 — Manifest com datas faltantes (IND):** As linhas abaixo não têm data_inicio_pdf/data_fim_pdf; isso enfraquece rastreabilidade.

| report_id                 | arquivo_pdf                   | snapshot   |   janela_anos | serie        |
|:--------------------------|:------------------------------|:-----------|--------------:|:-------------|
| REL_IND_D12M_SP500_PR_20Y | REL_IND_D12M_SP500_PR_20Y.pdf | D-12m      |            20 | SP500_BRL_PR |
| REL_IND_D12M_SP500_TR_20Y | REL_IND_D12M_SP500_TR_20Y.pdf | D-12m      |            20 | SP500_BRL_TR |

- **P3 — CMP no manifest sem datas:** Os 15 PDFs CMP estão sem data_inicio_pdf/data_fim_pdf. Se os CMP não exibirem datas, registrar em observacoes; se exibirem, preencher. Não bloqueia Gate 02 (foco IND), mas melhora rastreabilidade.


## (A) QA mecânico — checagens (100% da base)

- PDF bundle vs manifest (md5+size): **PASS (120/120)**
- RAW_METRICS vs manifest (md5): **PASS (105/105)**
- Chave única RAW_METRICS (cut,window,series): **PASS (duplicatas=0)**
- Cobertura por corte (5/10/15/20/25 × 7 séries): **PASS (35 por corte; 105 total)**
- NA em métricas críticas (RAW_METRICS): **PASS (0 NA)**
- MONTHLY_LONG sem duplicatas (report_id,date): **PASS (0)**
- MONTHLY_LONG continuidade mensal (sem gaps): **PASS (0 gaps em 105 séries)**
- Consistência matemática: total_return ≈ Π(1+ret)-1: **PASS (max|dif|=0.033586)**
- Vol anualizada: std(mensal)*sqrt(12): **PASS (dif máx ~0)**
- worst_month / best_month / pct_neg_months derivadas do mensal: **PASS (dif máx ~0)**
- Alinhamento datas finais por corte: **PASS (D0=10/02/2026; D12M=10/02/2025; D6M=08/08/2025)**


## (B) Auditoria amostral PDF → Planilha (com evidência)

- Método: amostra determinística (seed=20260214); 18 itens estratificados (3 cortes × 2 janelas × 3 séries) + 12 aleatórios.
- Métricas comparadas diretamente no PDF (página 1): **Rentabilidade acumulada**, **CAGR**, **Menor retorno mensal**, **datas início/fim**.
- Observação: **Volatilidade** e **Sharpe** no PDF seguem a definição da plataforma; na planilha, vol/sharpe/sortino são **derivados de retornos mensais** (excesso CDI), logo podem divergir — registrados apenas como referência.

### Sumário da amostra (30 itens)

| cut_snapshot   | window_label   | sheet_series   | report_id                 | pdf_file                      | overall_pass   |
|:---------------|:---------------|:---------------|:--------------------------|:------------------------------|:---------------|
| D0             | 5Y             | CDI            | REL_IND_D0_CDI_5Y         | REL_IND_D0_CDI_5Y.pdf         | True           |
| D0             | 5Y             | IBOV           | REL_IND_D0_IBOV_5Y        | REL_IND_D0_IBOV_5Y.pdf        | True           |
| D0             | 5Y             | PB             | REL_IND_D0_PB_5Y          | REL_IND_D0_PB_5Y.pdf          | True           |
| D0             | 25Y            | CDI            | REL_IND_D0_CDI_25Y        | REL_IND_D0_CDI_25Y.pdf        | True           |
| D0             | 25Y            | IBOV           | REL_IND_D0_IBOV_25Y       | REL_IND_D0_IBOV_25Y.pdf       | True           |
| D0             | 25Y            | PB             | REL_IND_D0_PB_25Y         | REL_IND_D0_PB_25Y.pdf         | True           |
| D6M            | 5Y             | CDI            | REL_IND_D6M_CDI_5Y        | REL_IND_D6M_CDI_5Y.pdf        | True           |
| D6M            | 5Y             | IBOV           | REL_IND_D6M_IBOV_5Y       | REL_IND_D6M_IBOV_5Y.pdf       | True           |
| D6M            | 5Y             | PB             | REL_IND_D6M_PB_5Y         | REL_IND_D6M_PB_5Y.pdf         | True           |
| D6M            | 25Y            | CDI            | REL_IND_D6M_CDI_25Y       | REL_IND_D6M_CDI_25Y.pdf       | True           |
| D6M            | 25Y            | IBOV           | REL_IND_D6M_IBOV_25Y      | REL_IND_D6M_IBOV_25Y.pdf      | True           |
| D6M            | 25Y            | PB             | REL_IND_D6M_PB_25Y        | REL_IND_D6M_PB_25Y.pdf        | True           |
| D12M           | 5Y             | CDI            | REL_IND_D12M_CDI_5Y       | REL_IND_D12M_CDI_5Y.pdf       | True           |
| D12M           | 5Y             | IBOV           | REL_IND_D12M_IBOV_5Y      | REL_IND_D12M_IBOV_5Y.pdf      | True           |
| D12M           | 5Y             | PB             | REL_IND_D12M_PB_5Y        | REL_IND_D12M_PB_5Y.pdf        | True           |
| D12M           | 25Y            | CDI            | REL_IND_D12M_CDI_25Y      | REL_IND_D12M_CDI_25Y.pdf      | True           |
| D12M           | 25Y            | IBOV           | REL_IND_D12M_IBOV_25Y     | REL_IND_D12M_IBOV_25Y.pdf     | True           |
| D12M           | 25Y            | PB             | REL_IND_D12M_PB_25Y       | REL_IND_D12M_PB_25Y.pdf       | True           |
| D6M            | 15Y            | SP500_TR       | REL_IND_D6M_SP500_TR_15Y  | REL_IND_D6M_SP500_TR_15Y.pdf  | True           |
| D6M            | 15Y            | IBOV           | REL_IND_D6M_IBOV_15Y      | REL_IND_D6M_IBOV_15Y.pdf      | True           |
| D0             | 25Y            | SP500_PR       | REL_IND_D0_SP500_PR_25Y   | REL_IND_D0_SP500_PR_25Y.pdf   | True           |
| D0             | 10Y            | PC             | REL_IND_D0_PC_10Y         | REL_IND_D0_PC_10Y.pdf         | True           |
| D12M           | 10Y            | SP500_TR       | REL_IND_D12M_SP500_TR_10Y | REL_IND_D12M_SP500_TR_10Y.pdf | True           |
| D6M            | 5Y             | PC             | REL_IND_D6M_PC_5Y         | REL_IND_D6M_PC_5Y.pdf         | True           |
| D12M           | 20Y            | SP500_PR       | REL_IND_D12M_SP500_PR_20Y | REL_IND_D12M_SP500_PR_20Y.pdf | True           |
| D6M            | 10Y            | SP500_PR       | REL_IND_D6M_SP500_PR_10Y  | REL_IND_D6M_SP500_PR_10Y.pdf  | True           |
| D12M           | 15Y            | SP500_PR       | REL_IND_D12M_SP500_PR_15Y | REL_IND_D12M_SP500_PR_15Y.pdf | True           |
| D6M            | 15Y            | PC             | REL_IND_D6M_PC_15Y        | REL_IND_D6M_PC_15Y.pdf        | True           |
| D0             | 15Y            | PA             | REL_IND_D0_PA_15Y         | REL_IND_D0_PA_15Y.pdf         | True           |
| D0             | 10Y            | CDI            | REL_IND_D0_CDI_10Y        | REL_IND_D0_CDI_10Y.pdf        | True           |


**Arquivo completo da auditoria:** `Gate02_PDF_to_Sheet_Audit_v13b.csv`

## (C) Validação cruzada externa (sanity check)

**Sanity check externo (CDI):** comparação pontual com a série mensal CDI/Over (Ipeadata, série 32237) para meses completos dentro da janela **D0 + 5Y**.

- Observação importante: como o estudo usa início/fim **no meio do mês** (10/02/2021 e 10/02/2026), os meses de **fev/2021** e **fev/2026** são parciais no Mais Retorno — não devem bater com o CDI “mês cheio” do IPEA/BCB. O sanity check foi feito em **meses cheios** entre esses extremos (mar/2021 … jan/2026).
- Exemplos (IPEA → Mais Retorno, valores em % no mês):
  - 2021.03: **0,2000%** ↔ **0,20%** no MONTHLY_LONG (REL_IND_D0_CDI_5Y). citeturn21view0
  - 2025.07: **1,2800%** ↔ **1,28%** no MONTHLY_LONG (REL_IND_D0_CDI_5Y). citeturn21view1
  - 2026.01: **1,1600%** ↔ **1,16%** no MONTHLY_LONG (REL_IND_D0_CDI_5Y). citeturn21view1

Resultado: **coerência forte** para CDI (meses cheios), consistente com a hipótese de que a série CDI do snapshot não contém erro grosseiro de plataforma.

## Ações recomendadas

1) **Atualizar `pdf_manifest_v13b.csv`**:
   - Preencher `data_inicio_pdf`/`data_fim_pdf` para:
     - `REL_IND_D12M_SP500_PR_20Y`
     - `REL_IND_D12M_SP500_TR_20Y`
   - Preencher `observacoes` para **todas as linhas D-6m**: “D-6m alvo 10/08/2025 (domingo) → usado 08/08/2025 (último dia anterior)”.
   - (Opcional) adicionar observação equivalente para CMP (ou preencher datas se existirem no PDF).
2) Após isso, republicar o bundle **sem alterar números** (apenas metadados) como `v13c` (ou manter v13b e versionar manifest como `v13b1`).
