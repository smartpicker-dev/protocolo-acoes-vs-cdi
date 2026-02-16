# Resultados (v13b1)

Esta seção descreve, de forma estritamente descritiva, os resultados consolidados nas **Tabelas 1–3** e **Figuras 1–4**, para três datas de corte (snapshots): **D0 = 2026-02-10**, **D-6m = 2025-08-08** e **D-12m = 2025-02-10**.

**Fonte (tabelas e figuras):** Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS.

### 5.1 Retorno total e CAGR (Tabela 1; Figuras 1 e 2)

A **Tabela 1** (`T1_total_return_CAGR_v13b1.csv`) reporta, para cada `cut×window×series`, o **retorno total acumulado** (`total_return`, em decimal) e o **CAGR** (`cagr`, em decimal). A **Figura 1** plota o valor final de R$1 como **multiplicador** (1 + `total_return`), e a **Figura 2** plota o CAGR convertido para **% a.a.** a partir de `cagr` (mesma ordenação de séries).

No snapshot **D0**, na janela **25Y**, o maior retorno acumulado é observado no **Portfólio C (TR)** (`total_return`=52.0951; multiplicador final = 1 + `total_return` = 53.0951x), com **`cagr`=0.1753**. No mesmo recorte (D0, 25Y), os benchmarks apresentam **CDI** (`total_return`=15.593; multiplicador final = 16.593x; `cagr`=0.1193) e **Ibovespa** (`total_return`=9.9907; `cagr`=0.1024). Para o **S&P 500 em BRL**, em D0, 25Y, observa-se `total_return`=20.886 e `cagr`=0.1317 para a série **Total Return**, versus `total_return`=12.7009 e `cagr`=0.1106 para a série **Price Return**.

Ainda em **D0**, o líder por **CAGR** varia por janela: **5Y** (Portfólio B (TR), `cagr`=0.2073); **10Y** (Portfólio B (TR), `cagr`=0.264); **15Y** (S&P 500 BRL (Total Return), `cagr`=0.228); **20Y** (S&P 500 BRL (Total Return), `cagr`=0.1601); **25Y** (Portfólio C (TR), `cagr`=0.1753). As Figuras 1 e 2 apresentam, no mesmo layout, esses resultados também para **D-6m** e **D-12m**, permitindo comparar a sensibilidade à data final.

### 5.2 Risco (Tabela 2; Figuras 3a e 3b)

A **Tabela 2** (`T2_risk_core_v13b1.csv`) reporta métricas de risco derivadas da série mensal: volatilidade anualizada (`vol_ann`), Sharpe e Sortino do excesso vs CDI (`sharpe_excess_cdi`, `sortino_excess_cdi`), máximo drawdown (`max_drawdown`), fração de meses negativos (`pct_neg_months`), pior e melhor mês (`worst_month`, `best_month`) e número de observações mensais (`N_months`). As **Figuras 3a** e **3b** sintetizam, respectivamente, `vol_ann` e `max_drawdown` para **D0 / D-6m / D-12m** em todas as janelas.

No snapshot **D0**, na janela **25Y**, a volatilidade anualizada do **CDI** é `vol_ann`=0.01283776240322256. No mesmo recorte, para os portfólios de ações, `vol_ann` varia de **Portfólio A (TR)** (0.21442462214197996) a **Portfólio C (TR)** (0.25395953615485023). Em termos de drawdown, em **D0, 25Y**, o **CDI** apresenta `max_drawdown`=0.0, enquanto os portfólios variam de **Portfólio A (TR)** (`max_drawdown`=-0.44219098274972823) a **Portfólio C (TR)** (`max_drawdown`=-0.5577921483097168). No mesmo recorte, `max_drawdown`=-0.4958952492027713 para **Ibovespa (TR)** e `max_drawdown`=-0.45822296554644304 para **S&P 500 BRL (Total Return)**.

Quanto à eficiência de risco (excesso vs CDI) em **D0, 25Y**, observa-se que o maior `sharpe_excess_cdi` entre os portfólios é do **Portfólio A (TR)** (`sharpe_excess_cdi`=0.3203011261348425); no mesmo recorte, **Ibovespa** apresenta `sharpe_excess_cdi`=0.046444853460341454. Em janela curta (ex.: **D0, 5Y**), o **Ibovespa** apresenta `sharpe_excess_cdi`=-0.00643798437944795, enquanto o **Portfólio B (TR)** apresenta `sharpe_excess_cdi`=0.5478473907420652 no mesmo recorte.

### 5.3 Robustez temporal (Tabela 3; Figura 4)

A **Tabela 3** consolida os outputs de robustez (`T3_robust_total_return_CAGR_v13b1.csv`, `T3_robust_risk_core_v13b1.csv`, `T3_robust_portfolio_ranking_v13b1.csv`) com **datas explícitas** por janela e snapshot (ex.: `end_date_D0`, `end_date_D6M`, `end_date_D12M`). A **Figura 4** resume, para os Portfólios A/B/C, o **range (max–min, em p.p.) do excesso de CAGR vs CDI** entre **D0 / D-6m / D-12m**, por janela.

No recorte de 5 anos, observa-se maior dispersão na sensibilidade temporal: o range do excesso de CAGR vs CDI (p.p.) é **PA=4.71**, **PB=9.53**, **PC=4.56**. Em 25 anos, os ranges são menores: **PA=0.32**, **PB=0.90**, **PC=0.49**.

Quanto ao critério “**excesso de CAGR vs CDI > 0** em **D0, D-6m e D-12m**”, a Tabela 3 indica que, na janela **5Y**, o **Portfólio B (TR)** apresenta `cagr_%_D12M`=8.74 versus **CDI** `cagr_%_D12M`=8.81 (sinal negativo do excesso no snapshot D-12m). Nas janelas **10Y–25Y**, os três portfólios (PA/PB/PC) apresentam excesso positivo em todos os três snapshots.

Por fim, o ranking entre **PA/PB/PC** (por CAGR) não é invariável ao deslocamento do snapshot em algumas janelas. Exemplos: em **10Y**, a ordem por CAGR se mantém em D0/D-6m/D-12m como ('PB', 'PC', 'PA'); em **5Y**, a ordem por CAGR em D0 é ('PB', 'PC', 'PA'), enquanto em D-6m e D-12m é ('PC', 'PA', 'PB').

**Fonte (tabelas e figuras):** Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS.
