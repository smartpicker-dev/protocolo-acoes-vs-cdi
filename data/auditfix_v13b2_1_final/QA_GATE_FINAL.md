# QA Gate Final — v13b2.1 (Hotfix T2) — Patch de verificação independente

Este QA complementa o `QA_GATE_FINAL.md` do bundle, adicionando verificação independente de extração mensal e reportando o overlap real entre janelas.

## Verificações executadas

1. **Dupla extração independente (mensal, IND):**

   - Método A: `pdfplumber` (texto da página com “Rentabilidade Histórica”).

   - Método B: `PyMuPDF/fitz` com reconstrução por coordenadas (`get_text('words')`) e agrupamento por linha.

   - Resultado: **0 divergências** mês-a-mês em **105/105** PDFs IND (todas as combinações de série×snapshot×janela).

2. **Recomputação das métricas (T2):**

   - Recomputadas a partir das séries mensais extraídas, com:

     - `vol_ann = std(mensal, ddof=1) * sqrt(12)`

     - `max_drawdown` no wealth index

     - `Sharpe` do excesso vs CDI: `mean(excesso)/std(excesso, ddof=1) * sqrt(12)`

     - `Sortino` do excesso vs CDI usando **downside deviation RMS**: `down = min(excesso,0)`; `dd = sqrt(mean(down^2))`; `mean(excesso)/dd*sqrt(12)`

   - Resultado: **0 divergências** (diferenças numéricas apenas de precisão de ponto flutuante ~1e-16).

3. **Invariantes de N (mensal):**

   - 5Y=61; 10Y=121; 15Y=181; 20Y=241; 25Y=301 — **PASS**.

4. **Gate PR vs TR:**

   - Nenhum caso de linha inteira idêntica `SP500_PR == SP500_TR` em T2 — **PASS**.

5. **Overlap entre janelas (diagnóstico do provedor):**

   - Ao comparar meses sobrepostos entre 25Y e janelas menores (20Y/15Y/10Y/5Y), foram detectadas divergências sistemáticas em praticamente todos os casos.

   - Isso indica que os relatórios IND por janela não preservam retornos mensais idênticos em meses sobrepostos.

   - O arquivo `overlap_report_v13b2_1_PATCH.csv` registra contagens por série/snapshot/janela (amostras de meses). **Isto não é tratado como erro de extração**, mas como inconsistência entre relatórios do provedor.


## Status

- **Extração mensal dupla:** PASS (0 divergências)

- **T2 recomputada vs mensais:** PASS

- **Overlap entre janelas:** **NÃO ZERA** (diagnóstico do provedor; ver relatório)


## Arquivos gerados neste patch

- `diff_full_T2_monthly_v13b2_1_PATCH.csv` (header-only; divergências=0)

- `overlap_report_v13b2_1_PATCH.csv`
