# Discussão, Limitações e Conclusão

## 3.1 Discussão

Contribuição e enquadramento. A principal contribuição do estudo é metodológica: um desenho reprodutível com janelas fixas e três snapshots pré-definidos (D0, D-6m, D-12m), além de trilha de auditoria e congelamento do bundle (v13b1 / Gate02 PASS). Como contribuição aplicada ao contexto brasileiro, em que o CDI é frequentemente tratado como um elevado custo de oportunidade, o estudo documenta de forma auditável que o diferencial “ações vs CDI” é sensível ao horizonte e à data final. Isso ajuda a reconciliar leituras de curto prazo com padrões observados em horizontes longos. A Discussão sintetiza os padrões risco–retorno observados, sem pretensão de inferir causalidade.

### 3.1.1 O que os resultados mostram

Em linhas gerais, as Tabelas 1–3 e as Figuras 1, 2, 3a, 3b e 4 mostram que, no recorte analisado, em parte dos recortes de horizontes mais longos, os Portfólios A/B/C exibem retornos totais e CAGRs superiores ao CDI e diferem dos benchmarks de mercado (ver Tabela 1; ver Figuras 1–2). Os Portfólios A/B/C são carteiras de regras fixas, deliberadamente não otimizadas ex ante, com pesos iguais no início e buy-and-hold sem rebalanceamento. No caso do S\&P 500 em BRL, “Price Return (PR)” denota a série sem reinvestimento de proventos e “Total Return (TR)” a série com reinvestimento teórico; em ambos os casos, a conversão para BRL incorpora a variação cambial BRL/USD. Em contrapartida, essas carteiras exibem risco substancialmente maior do que o CDI, refletido em maior volatilidade e maior drawdown máximo (ver Tabela 2; ver Figuras 3a/3b).

Em paralelo, combinando Tabela 1 (retorno) com Tabela 2 (risco), nos recortes analisados, retornos mais altos observados vêm acompanhados de risco materialmente maior do que o observado no CDI (na série acumulada do CDI utilizada neste snapshot, o índice é monotônico; por isso, o drawdown máximo medido pela métrica adotada é reportado como 0 na amostra), e a eficiência de risco (Sharpe/Sortino do excesso vs CDI) depende do horizonte: janelas mais longas tendem a produzir leituras mais estáveis do que janelas curtas (ver Tabelas 1–2; ver Figuras 3a/3b). A seção seguinte discute mecanismos plausíveis para essas divergências, sem atribuição causal.

### 3.1.2 Por que carteiras podem divergir de índices

Esta seção apresenta hipóteses plausíveis (não causais) para explicar por que carteiras de regras fixas, estáticas e concentradas podem divergir de índices amplos. As afirmações abaixo devem ser lidas como mecanismos potenciais, consistentes com a diferença de construção entre um portfólio de regras fixas, deliberadamente não-otimizado ex ante, com pesos iguais no início da janela (buy-and-hold, sem rebalanceamento) e índices com regras de elegibilidade e ponderação, sem pretensão de atribuir “qualidade” intrínseca às empresas nem de inferir “alfa” no sentido estatístico.

Embora a seleção de ativos seja discricionária, a simulação não implementa decisões dinâmicas típicas de gestão ativa (rebalanceamento, rotação, timing).

**(i) Objetivo de construção e regras quantitativas.**  
Índices de mercado são desenhados para representatividade, negociabilidade e replicabilidade, seguindo regras formais (ex.: critérios de elegibilidade, liquidez/presença, revisões periódicas e ponderação) e não têm como objetivo primário uma seleção *bottom-up* baseada em avaliação discricionária de fundamentos econômico-financeiros das empresas.   
Assim, é plausível que um portfólio de regras fixas e construção deliberadamente parcimoniosa, porém diferente na regra de ponderação e no conjunto de ativos, apresente desempenho distinto do índice, em qualquer direção, por diferenças mecânicas de construção e exposição. Esse contraste entre objetivos de desenho e regras formais de elegibilidade/ponderação é consistente com descrições metodológicas oficiais de índices (B3, 2021; B3, 2023). *(Para a descrição formal das regras de elegibilidade e ponderação dos índices, ver o pacote de metodologia de índices arquivado no pacote de replicação do estudo.)*

**(ii) Ponderação por valor de mercado (free float) vs pesos iguais no início da janela.**  
Os Portfólios A/B/C foram definidos com 8 ações e pesos iguais no início de cada janela, sem rebalanceamento.  
Mesmo sem invocar fatores formais, essa escolha implica exposições diferentes de um índice ponderado por valor de mercado ajustado por free float: em particular, um portfólio com pesos iguais (equal-weight) tende a dar maior participação relativa a nomes que não dominam o índice, enquanto um índice amplo tende a concentrar mais peso nas maiores posições elegíveis. Divergências de retorno e risco podem, portanto, ser compatíveis com diferenças de ponderação e concentração, e não necessariamente com “seleção superior”. Discussões sobre as implicações de diferentes esquemas de ponderação (valor de mercado vs equal-weight) e sobre o desempenho relativo de alocações ingênuas do tipo 1/N versus abordagens otimizadas são amplamente tratadas na literatura. (DEMIGUEL; GARLAPPI; UPPAL, 2009).

**(iii) Buy-and-hold sem rebalanceamento e “concentração endógena”.**  
Ao proibir rebalanceamento, a estratégia permite que vencedores históricos cresçam em peso ao longo do tempo (efeito de composição), enquanto perdedores podem ter seu peso relativo reduzido por simples queda de preço. Esse mecanismo pode produzir assimetria: resultados finais podem ser mais sensíveis à presença (ou ausência) de poucos “vencedores” dentro de um conjunto pequeno de ativos, o que é compatível com a maior exposição a risco observada nos portfólios (ver Tabela 2; ver Figuras 3a/3b). A sensibilidade do retorno agregado à presença de poucos “vencedores” é consistente com evidência de forte assimetria na contribuição de ações individuais para a criação de riqueza em horizontes longos (BESSEMBINDER, 2018).

**(iv) Universo efetivo (14 tickers) e potencial viés de sobrevivência/seleção por auditabilidade.**  
O protocolo explicita que o universo efetivo é a união das ações presentes nas carteiras A/B/C, totalizando 14 tickers, e que houve trade-off deliberado em favor de auditabilidade/reprodutibilidade.  
Esse desenho pode favorecer um conjunto de “sobreviventes” (por definição operacional e por restrições de auditabilidade) em relação a um índice dinâmico que entra e sai de componentes ao longo do tempo. O ponto não é afirmar que o estudo “removeu empresas ruins”, mas reconhecer que o recorte não é uma amostra estatística do mercado e que isso é uma limitação estrutural (ver também Notas técnicas). O impacto de viés de sobrevivência em inferências de desempenho é um tema clássico na literatura empírica e pode distorcer comparações quando a amostra exclui trajetórias que deixam de existir ao longo do tempo (ELTON; GRUBER; BLAKE, 1996).

**(v) S\&P 500 em BRL e efeito câmbio (registro, sem quantificação).**  
O benchmark S\&P 500 no estudo é expresso em BRL (nas variantes Price Return (PR) e Total Return (TR)).  
Portanto, além do comportamento do índice em USD e do tratamento de proventos (TR vs PR), há influência do câmbio BRL/USD embutida na série em BRL. Esta observação é meramente descritiva: o estudo não decompõe (nem quantifica) a contribuição do câmbio. O papel do risco cambial no retorno para o investidor doméstico em ativos internacionais é tratado classicamente em (ADLER; DUMAS, 1983).

### 3.1.3 Robustez temporal e implicações anti-cherry-picking

O protocolo pré-registra três snapshots (D0, D-6m, D-12m) e janelas fixas (5/10/15/20/25 anos), com regra explícita de não-pregão/sem dados.  
Na prática, o snapshot D-6m usa 08/08/2025 como data final efetiva por ajuste de não-pregão (alvo era 10/08/2025).  
Essa escolha reforça a disciplina anti-cherry-picking: em vez de ajustar retrospectivamente as datas finais por conveniência ex post, o estudo fixa a regra e registra o deslocamento quando necessário. Em termos interpretativos, isso limita inferências baseadas em janelas curtas e sugere que conclusões sobre o diferencial “ações vs CDI” dependem criticamente do horizonte e da data final.

Os resultados de robustez sugerem que janelas curtas são mais sensíveis à data final, enquanto janelas longas tendem a apresentar maior estabilidade relativa (ver Tabela 3; ver Figura 4).  
Em particular, o recorte de 5 anos exibe maior dispersão do excesso de CAGR vs CDI entre snapshots do que o recorte de 25 anos, e há casos em que o excesso de CAGR vs CDI não mantém o mesmo sinal nos três snapshots (ex.: Portfólio B em 5 anos no snapshot D-12m).

## 3.2 Limitações e ameaças à validade

### Validade interna

- Meses parciais e anualização: cortes em datas como 10/02 não coincidem com fechamento mensal; métricas baseadas em séries mensais (volatilidade, Sharpe/Sortino, drawdown) podem conter ruído residual de anualização.  
- Ajuste de calendário no D-6m: o snapshot D-6m usa 08/08/2025 por não-pregão, alterando levemente a janela em relação ao alvo teórico.  
- Sensibilidade em 5 anos: resultados e rankings podem variar mais em janelas curtas; por construção, inferências “fortes” a partir de 5 anos devem ser tratadas com cautela (ver Tabela 3).  
- Dependência de séries mensais para risco: as métricas de risco dependem de consistência e cobertura mensal no snapshot; quando há limitações, isso afeta diretamente a robustez das estatísticas de risco. Conforme os outputs de risco (ver Tabela 2\) e a nota metodológica de robustez (robustness\_summary\_v13b1.md), volatilidade, Sharpe/Sortino, drawdown e percentuais de meses negativos são derivados de séries mensais.

### Validade externa

- Retornos brutos (sem fricções): os resultados não incorporam custos de transação, spreads, emolumentos, tributação ou custos de veículo, o que tende a superestimar retorno líquido realizável.  
- Universo por conveniência/auditabilidade: o universo não é amostra estatística do mercado; é um conjunto pré-definido para permitir auditoria e replicação.  
- Viés de sobrevivência/seleção: a regra de exclusões e o foco em séries auditáveis podem produzir um conjunto de “sobreviventes” históricos; isso limita a extrapolação para “ações em geral”.  
- Rigidez do buy-and-hold: a simulação não inclui rebalanceamento, aportes, rotação tática ou otimização; portanto, não replica a prática típica de muitos investidores/gestores.

### Validade de construto

- CDI como proxy e risk-free operacional: o CDI é o benchmark primário e também a referência “risk-free” nos Sharpe/Sortino em excesso, o que pode influenciar interpretações (convenção local, não equivalência de risco).  
- Total Return como reinvestimento teórico: séries TR pressupõem reinvestimento teórico de proventos; na prática, reinvestimento pode sofrer fricções e restrições (lotes, custos, timing).  
- Proxy de risco incompleta: volatilidade e drawdown capturam dimensões relevantes de risco de mercado, mas não esgotam riscos (liquidez, governança, eventos idiossincráticos), especialmente em carteiras com apenas 8 ativos.

### Escopo e universo efetivo

- Universo efetivo \= 14 tickers (união A/B/C; ver Apêndice A).  
- Implicação: trata-se de um estudo de caso histórico com desenho reprodutível e auditável, e não de uma “prova” universal sobre ações brasileiras.

## 3.3 Conclusão

Os resultados consolidados nas Tabelas 1–3 e nas Figuras 1, 2, 3a, 3b e 4 indicam que, no recorte analisado e sob regras fixas (janelas pré-definidas; retorno total no snapshot), os Portfólios A/B/C — carteiras de regras fixas, deliberadamente não otimizadas ex ante (conjunto reduzido; pesos iguais no início; buy-and-hold sem rebalanceamento) — em parte dos recortes de horizontes longos exibem superação do CDI, ao custo de maior volatilidade e maior drawdown máximo (ver Tabelas 1–2; ver Figuras 1, 2, 3a, 3b e 4).

Ao mesmo tempo, a análise de robustez reforça que conclusões em janelas curtas são mais sensíveis à data final, enquanto horizontes longos tendem a ser mais estáveis — sem eliminar limitações estruturais (universo efetivo de 14 tickers, ausência de fricções e natureza não representativa do recorte) (ver Tabela 3; ver Figura 4).

Assim, trata-se de um estudo de caso histórico, reprodutível e auditável, com finalidade metodológica e ilustrativa, destinado a documentar trade-offs risco–retorno e procedimentos de mitigação de cherry-picking, sem pretensão de inferir causalidade ou oferecer recomendação de investimento.

**Disponibilidade de dados e reprodutibilidade (Capítulo 3).** As Tabelas 1–3 e as Figuras 1–4 deste capítulo são derivadas exclusivamente de relatórios PDF exportados da plataforma Mais Retorno (sob licença comercial), consolidados no bundle v13b1 e validados no Gate02 PASS. As tabelas e figuras são geradas a partir de outputs canônicos versionados e listados no pacote de replicação, juntamente com manifestos e checksums para verificação de integridade. **Por restrições de licença de dados de terceiros, os PDFs exportados e o conteúdo bruto da plataforma não são redistribuídos publicamente; pesquisadores com acesso ao Mais Retorno podem reproduzir os resultados seguindo os IDs, manifestos e as instruções do pacote de replicação.**  
**Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS.**

