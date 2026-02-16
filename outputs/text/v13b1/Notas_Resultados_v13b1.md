# Notas técnicas — Resultados (v13b1)

- **Ajuste não-pregão (D-6m):** a data alvo teórica era **10/08/2025**; por cair em fim de semana (não-pregão), o snapshot **D-6m** usa **08/08/2025** como data final efetiva.
- **Snapshots (datas finais efetivas):** D0=2026-02-10; D-6m=2025-08-08; D-12m=2025-02-10.
- **Unidade em Tabela 1:** `total_return` é **decimal** (ex.: 15.59 = 1559%); quando usado multiplicador em figura/texto, aplica-se **1 + total_return**.
- **Métrica primária (rentabilidade):** `total_return` e `cagr` são tratados como **canônicos do PDF** (snapshot), por desenho do bundle v13b1, para evitar divergências de arredondamento ao encadear retornos mensais.
- **Meses parciais (cortes no meio do mês):** as datas de corte (ex.: 10/02/2026) não coincidem necessariamente com fechamento mensal; métricas baseadas em série mensal (ex.: `vol_ann`, Sharpe/Sortino) podem ter ruído residual de anualização.
- **CDI como benchmark/proxy e risk-free:** o CDI é usado como benchmark primário e como taxa livre de risco nos cálculos de `sharpe_excess_cdi` e `sortino_excess_cdi`; leituras devem considerar essa convenção operacional.
- **Custos, impostos e fricções:** resultados são **brutos** (sem corretagem, emolumentos, spreads, imposto de renda ou custos de veículo), o que limita inferências sobre retorno líquido.
- **Estratégia simulada:** buy & hold estático no período da janela (sem rebalanceamento de pesos, sem trocas de ativos durante a janela).
- **Universo efetivo:** **14 tickers** (união das carteiras A/B/C); trata-se de universo pré-definido do protocolo, não de amostra estatística do mercado.
- **Total Return vs Price Return:** salvo séries explicitamente rotuladas como **Price Return** (ex.: `SP500_PR`), as demais séries são tratadas como **Total Return** (reinvestimento teórico de proventos), conforme o dicionário de métricas v13b1.
