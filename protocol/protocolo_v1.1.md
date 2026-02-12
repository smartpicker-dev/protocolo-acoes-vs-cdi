**Protocolo v1.1 — Ações vs CDI (simulação educacional reprodutível)**

Versão: 1.1  
Data de congelamento: 12/02/2026  
Âncora (D0): 10/02/2026  
Escopo: simulação educacional (estudo de caso). Não é recomendação.  
Plataforma: Mais Retorno (maisretorno.com)  
Regra de mudanças: qualquer alteração após este congelamento vira versão 1.2 e exige justificativa escrita (o que mudou, por quê, impacto esperado).

Changelog:  
v1.1 — Substituição por auditabilidade (pré-coleta): KLBN3 apresentou histórico mensal incompleto no Mais Retorno (ex.: relatório 25Y no corte D-12m indica Qtd.M=251, abaixo do esperado), reduzindo reprodutibilidade e QA. Substituição: KLBN3 → GGBR3 no Portfólio B, mantendo a regra setorial (economia real: indústria/metais). Demais parâmetros (D0/janelas, pesos iguais, buy & hold sem rebalance, benchmarks, métricas e robustez) permanecem inalterados.

1\) Pergunta e objetivo

Pergunta (formal):  
Em janelas fixas de 5, 10, 15, 20 e 25 anos encerradas em D0, qual foi o desempenho (em retorno total) de três carteiras hipotéticas buy & hold de ações brasileiras (Portfólios A/B/C), em comparação ao CDI (benchmark primário) e aos benchmarks adicionais Ibovespa e S\&P 500 em BRL (Price Return e Total Return), usando regras simples, transparentes e reproduzíveis? Quão sensível é esse resultado a mudanças pré-definidas na data final (robustez D-6m e D-12m)?

Objetivo:  
Comparar, de forma simples, transparente e reproduzível, o desempenho de 3 carteiras hipotéticas buy & hold versus CDI (e benchmarks adicionais) em janelas fixas, com regras simples e auditáveis, usando retorno total e um conjunto “core” de métricas de risco/retorno, sem cherry-picking de datas, ativos ou pesos.

2\) Regras anti–cherry-picking (pré-registradas)

\- Datas fixas e “redondas”, ancoradas em D0=10/02/2026.  
\- Proibido ajustar datas após ver resultados.  
\- Qualquer mudança depois do congelamento → Protocolo v1.2 com justificativa escrita.

Janelas (encerradas em D0):  
\- 25 anos: 10/02/2001 → 10/02/2026  
\- 20 anos: 10/02/2006 → 10/02/2026  
\- 15 anos: 10/02/2011 → 10/02/2026  
\- 10 anos: 10/02/2016 → 10/02/2026  
\- 5 anos:  10/02/2021 → 10/02/2026

Regra de não-pregão/sem dado:  
Usar o último dia disponível anterior no Mais Retorno, e registrar isso no log de coleta.

3\) Universo e elegibilidade

Universo core (15 nomes, tickers atuais):  
BBDC3, BBAS3, ITUB3, PETR3, VALE3, CMIG3, CPLE3, EGIE3, VIVT3, SBSP3, ABEV3, LEVE3, CSNA3, KLBN3, GGBR3.

Exclusões (regras):  
\- Outliers extremos no período que possam distorcer por concentração (ex.: WEG, Unipar) — regra conservadora.  
\- Quebras/reestruturações profundas (para evitar viés de “empresa que não sobreviveu”).  
\- Tickers difíceis de auditar por mudanças complexas (fusões/reorganizações) que prejudiquem reprodutibilidade.  
\- Série mensal incompleta ou materialmente inconsistente na fonte primária (Mais Retorno) para uma janela/corte exigidos, quando isso impedir QA e replicação.

Trade-off explícito:  
Priorizar auditabilidade/reprodutibilidade em detrimento de abrangência.

4\) Carteiras e regras publicáveis

3 carteiras (A/B/C), 8 ações, pesos iguais no início de cada janela.  
Rebalanceamento: NÃO (buy & hold puro).  
Sem rotação tática, sem otimização ex-post.

Regra de composição (publicável, ex-ante)  
Para reduzir qualquer acusação de seleção “na mosca”, a composição das carteiras segue uma regra simples baseada em blocos setoriais. Cada portfólio tem 8 ações, pesos iguais no início de cada janela, buy & hold sem rebalanceamento, e mantém uma estrutura semelhante (âncoras \+ diversificação), variando apenas parte dos componentes.

Âncoras do mercado (2 ações fixas)  
Selecionamos 2 empresas de alta representatividade e liquidez como âncoras presentes em todos os portfólios: PETR3 e VALE3.

Financeiro (2 ações)  
Incluímos 2 bancos do bloco Financeiro por serem pilares do mercado brasileiro, escolhidos em rodízio dentre BBDC3, BBAS3 e ITUB3, conforme a carteira.

Infra/Utilidades (2 ações)  
Incluímos 2 empresas do bloco de Energia/Utilidades para representar negócios regulados/infraestrutura, escolhidas em rodízio dentre CMIG3, CPLE3 e EGIE3, conforme a carteira.

Economia real (2 ações)  
Incluímos 2 empresas de economia real, escolhidas em rodízio dentre os blocos abaixo, para diversificação fora de bancos/commodities/utilities:  
\- Telecom/Saneamento: VIVT3, SBSP3  
\- Consumo não cíclico: ABEV3  
\- Consumo cíclico (autopeças): LEVE3  
\- Indústria/metais e papel e celulose: CSNA3, KLBN3, GGBR3

Resultado  
Cada carteira mantém a mesma “espinha dorsal” (âncoras \+ financeiro \+ utilidades) e varia os componentes de economia real, permitindo comparar misturas setoriais diferentes sem depender de um único conjunto “campeão”.

Cláusula de blindagem (instanciação congelada)  
As carteiras A/B/C listadas abaixo são a instanciação fixa desta regra para este estudo, congelada na versão 1.1; qualquer alteração de ativos, pesos, número de ações, ou dos blocos setoriais definidos acima exige versão 1.2 com justificativa explícita.

Carteiras (congeladas):  
\- Portfólio A: PETR3, VALE3, ITUB3, BBAS3, CMIG3, EGIE3, ABEV3, VIVT3  
\- Portfólio B: PETR3, VALE3, BBDC3, ITUB3, CPLE3, EGIE3, GGBR3, SBSP3  
\- Portfólio C: PETR3, VALE3, BBAS3, BBDC3, CMIG3, CPLE3, CSNA3, LEVE3

5\) Dados e fontes (Mais Retorno)

Fonte primária:  
PDFs/relatórios exportados do site Mais Retorno (maisretorno.com), gerados como “snapshot” do estudo e arquivados junto com os parâmetros do comparador (prints e/ou cabeçalho do relatório), datas exatas e composição das carteiras.

Definições operacionais (Mais Retorno):  
\- Total Return inclui, além da variação de preço, pagamentos como dividendos/rendimentos/cupom.  
\- Price Return considera apenas a variação do preço (sem esses pagamentos).  
\- A plataforma descreve correções/ajustes em gráficos associados a distribuição de rendimentos e desdobramentos/grupamentos, com explicação do mecanismo.

Benchmarks (séries do Mais Retorno):  
\- CDI (benchmark primário)  
\- IBOV (Ibovespa)  
\- S\&P 500 em BRL — Price Return  
\- S\&P 500 em BRL — Total Return

Regra de consistência (snapshot):  
O D0 efetivo de cada corte (D0, D-6m, D-12m) é a data final contida no PDF/export arquivado. Se houver diferença de “última atualização” entre séries, adota-se a data comum mais recente disponível para todos os benchmarks no snapshot, e isso é registrado no log.

6\) Métrica primária e secundárias (core set)

Métrica primária (congelada):  
Retorno total acumulado no período (por janela e por série), obtido a partir do snapshot do Mais Retorno.

Métricas secundárias (core, congeladas):  
\- CAGR  
\- Volatilidade anualizada (a partir de retornos mensais; regra de anualização documentada)  
\- Sharpe  
\- Sortino  
\- Máximo drawdown  
\- % de meses negativos  
\- pior mês

Regra de contingência:  
Se o snapshot não permitir retornos mensais consistentes para todas as séries/janelas, o core set reduz para Retorno total acumulado \+ CAGR \+ Máximo drawdown, e as demais métricas migram para apêndice ou são removidas (sem forçar cálculo inconsistente).

7\) Plano de análise (outputs fechados)

Tabelas (planejadas):  
\- T1: Retorno acumulado e CAGR por janela (A/B/C vs CDI vs IBOV vs S\&P 500 Price Return/Total Return).  
\- T2: Core set de risco (Vol, Sharpe, Sortino, Max drawdown, % meses negativos, pior mês) por janela.  
\- T3: Robustez (D0/D-6m/D-12m) — repetir o core set e destacar mudanças de ranking e magnitude.

Figuras (planejadas):  
\- F1: Curvas de crescimento (base 100\) por janela, comparando Portfólios A/B/C e benchmarks.  
\- F2: Drawdown ao longo do tempo (por janela; pelo menos para Portfólios e IBOV).  
\- F3: Barras de CAGR e Vol (visão risco-retorno por janela).

Ordem de leitura (fechada):  
F1 → T1 → T2 → F2 → Robustez (T3) → Limitações.

8\) Robustez (pré-definida)

Repetir o core set para três datas finais (snapshots):  
\- D0 \= 10/02/2026  
\- D-6m \= 10/08/2025  
\- D-12m \= 10/02/2025

Regra:  
Se a data cair em dia sem pregão/sem dado na plataforma, usar o último dia disponível anterior e registrar isso no log.

9\) Auditoria e validação (QA)

QA da base (obrigatório):  
\- Checar gaps/duplicatas/valores ausentes.  
\- Checar retornos impossíveis/anomalias grosseiras (ex.: saltos incoerentes não explicados por evento).  
\- Consistência matemática: retorno acumulado vs encadeamento de retornos periódicos.

Validação cruzada amostral (obrigatória):  
\- Selecionar 2–3 ativos \+ CDI e comparar início/fim (e/ou alguns retornos mensais) com fonte alternativa, apenas como sanity check.  
\- Registrar divergências e tratá-las como ameaça à validade.

10\) Limitações e ameaças à validade

\- Viés de sobrevivência e universo por conveniência.  
\- Ausência de custos, spreads, impostos PF e fricções.  
\- Dependência da metodologia/dados do Mais Retorno.  
\- Risco de ações ≠ risco CDI; o estudo não prova “prêmio de risco” universal.  
\- Não generaliza para “todas as ações” nem para “qualquer seleção”.

11\) Declarações

\- Finalidade educacional; sem recomendação de compra/venda; sem promessa de retorno.  
\- Conflito de interesse: autor é gestor e tem interesse institucional no tema “ações vs renda fixa”. Isso é declarado por transparência.

12\) O que NÃO será feito (anti-monstro)

\- Não ajustar carteiras ou datas pós-resultados.  
\- Não expandir universo além do core (a menos que vire v1.2).  
\- Não incluir modelagem detalhada de custos/impostos (apenas discussão qualitativa).  
\- Não incluir otimização, rebalanceamento, timing, ou seleção ex-post por desempenho.  
\- Não fazer inferência causal/estatística pesada no corpo principal; se existir, será apêndice e não muda a conclusão principal.

Assinatura do protocolo (v1.1)  
Autor: Patrick Gerard Pin —  Data: 12/02/2026  
Declaração de congelamento: “Qualquer mudança depois disso é versão 1.2 e precisa justificativa.”

