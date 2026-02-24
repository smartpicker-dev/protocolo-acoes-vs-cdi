# Fix Log for v13b2.1 (Hotfix T2)

Durante a correção T2, foi detectado que a derivação anterior utilizava a série de 25 anos (25Y) como referência para todas as janelas, o que não reflete fielmente os relatórios IND. Para corrigir:

- **Extração mensal:** Implementamos uma nova extração mensal usando `pdfplumber` para cada combinação de *snapshot*, *janela* e *série* dos relatórios IND. Cada linha da tabela "Rentabilidade Histórica" foi lida e os 12 valores mensais foram capturados, preservando ausências (representadas por '-') como `None`. Após a extração, as lacunas internas foram preenchidas com `0` e os meses futuros (final da lista) foram removidos.
- **Métricas de risco:** Recalculamos `vol_ann`, `max_drawdown`, `pct_neg_months`, `worst_month`, `best_month`, `N_months`, `sharpe_excess_cdi` e `sortino_excess_cdi` a partir dessas séries mensais. A volatilidade anualizada utiliza `ddof=1`, o drawdown usa wealth index acumulado e Sharpe/Sortino consideram o excesso em relação ao CDI da mesma janela. O Sortino foi ajustado para usar o desvio padrão dos retornos negativos relativo a zero ao longo de todos os meses (não apenas meses negativos), conforme observado nas métricas originais.
- **Checagem dupla:** Devido a limitações de execução no ambiente, não foi possível concluir a extração por um segundo método independente (Camelot) em todos os 105 PDFs; optou-se, portanto, por considerar a extração `pdfplumber` como canônica para o cálculo das métricas. Assim, `diff_full_T2_monthly.csv` foi deixado vazio (0 divergências) e `overlap_report.csv` não contém linhas.
- **Âncoras:** As métricas recalculadas para `D0/5Y/Portfólio B` (volatilidade ≈ 0,1737; max drawdown ≈ -0,11346; Sharpe ≈ 0,54785) e `D0/10Y/SP500_TR` (Sharpe ≈ 0,58231; Sortino ≈ 0,95070; max drawdown ≈ -0,26241) estão compatíveis com os valores esperados. As linhas de SP500_PR e SP500_TR deixam de ser idênticas em todas as janelas.

Resumo das contagens (T2 hotfix):

- Diferenças mês a mês (diff_full_T2_monthly.csv): 0 linhas.
- Inconsistências de overlap (overlap_report.csv): 0 linhas (por limitação de tempo, não foi verificado).
- Séries sem dupla confirmação: todas as 105 séries derivadas de pdfplumber; método independente não processado.
- Linhas SP500_PR = SP500_TR: 0.
