# 2. Metodologia

## 2.1 Desenho do estudo e objetivo
Este estudo conduz uma análise histórica observacional e reprodutível (estudo de caso) para comparar o desempenho de três carteiras hipotéticas de ações brasileiras (Portfólios A/B/C) em regime **buy-and-hold**, frente ao **CDI** (benchmark primário) e a benchmarks adicionais (**Ibovespa** e **S&P 500 em BRL**, nas variantes **Price Return** e **Total Return**). O desenho enfatiza regras pré-definidas para reduzir graus de liberdade analítica (datas, janelas e composições) e, com isso, tornar o procedimento auditável. Uma cautela de escopo: o estudo descreve desempenho histórico segundo as regras adotadas e não constitui recomendação de investimento.

## 2.2 Pré-registro, fonte de dados e congelamento
O plano do estudo foi **pré-registrado** em protocolo congelado (v1.3; data de congelamento: **14/02/2026**), que define pergunta, amostra operacional, janelas, snapshots, métricas e regras anti–cherry-picking. A fonte primária consiste em **relatórios em PDF exportados** da plataforma **Mais Retorno**, tratados como instantâneos (“snapshots”) do comparador na data de geração, preservando os parâmetros do recorte e as séries reportadas no próprio relatório.

Os materiais foram consolidados em um pacote congelado (v13b1) com controle de qualidade (Gate02 PASS).

## 2.3 Carteiras e benchmarks (definições operacionais)
### 2.3.1 Carteiras A/B/C
Foram consideradas três carteiras hipotéticas (A/B/C), cada uma composta por **8 ações**, com **pesos iguais no início** de cada janela. A estratégia é **buy-and-hold**, **sem rebalanceamento** e sem rotação de ativos ao longo da janela. A composição integral dos Portfólios A/B/C e a definição do universo efetivo constam no **Apêndice A**.

### 2.3.2 Benchmarks
Os benchmarks analisados (conforme disponibilizados na plataforma fonte) são:
- **CDI** (benchmark primário);
- **Ibovespa (IBOV)**;
- **S&P 500 em BRL — Price Return (PR)**;
- **S&P 500 em BRL — Total Return (TR)**.

Operacionalmente, **Total Return (TR)** incorpora variação de preço e componentes de retorno distribuído conforme a série reportada, enquanto **Price Return (PR)** captura apenas a variação de preço, também conforme a série reportada.

## 2.4 Datas, snapshots e janelas
### 2.4.1 Snapshots (datas finais) e regra de não-pregão/sem dado
A análise utiliza três snapshots com datas finais pré-definidas:
- **D0 = 10/02/2026**
- **D-6m = 08/08/2025** (ajuste por não-pregão conforme regra)
- **D-12m = 10/02/2025**

Regra operacional: quando a data alvo não estiver disponível na série (não-pregão/sem dado), adota-se o **último dia disponível anterior**, registrando-se o ajuste na trilha de auditoria do pacote congelado.

### 2.4.2 Janelas fixas
As comparações são conduzidas em janelas fixas de **5, 10, 15, 20 e 25 anos**, encerradas na data final do snapshot correspondente. A definição de janelas “redondas” e imutáveis é parte do pré-registro e visa reduzir escolhas ex post de horizonte temporal.

## 2.5 Métricas
A métrica primária é o **retorno total acumulado** por janela e por série (carteiras e benchmarks), conforme reportado no snapshot.

Como métricas secundárias (“core”), o protocolo define:
- **CAGR**;
- **volatilidade anualizada** (a partir de retornos mensais quando aplicável);
- **drawdown máximo**;
- **Sharpe** e **Sortino** com base em **excesso vs CDI**;
- estatísticas descritivas de retorno mensal (por exemplo, **percentual de meses negativos** e **pior mês**), quando reportadas.

Os retornos totais acumulados e CAGRs por janela estão na **Tabela 1**; a síntese visual está nas **Figuras 1–2**.  
As medidas de risco (volatilidade anualizada, drawdown máximo, Sharpe/Sortino vs CDI) estão na **Tabela 2** e nas **Figuras 3a/3b**.  
A análise de robustez por snapshots está na **Tabela 3** e na **Figura 4**.

## 2.6 Procedimento de cálculo, convenções e consistência
As estatísticas por janela são tratadas como medidas no ponto final da janela (data final do recorte) definida: para cada carteira/benchmark e para cada janela, utiliza-se o retorno total acumulado reportado no snapshot e, quando aplicável, séries mensais associadas ao mesmo recorte para compor métricas de risco.

As métricas baseadas em retornos mensais seguem convenções usuais: anualização de medidas de dispersão a partir da frequência mensal e cálculo de **excesso em relação ao CDI** para Sharpe/Sortino, conforme definido no protocolo. Para preservar consistência entre séries/janelas, o pré-registro estabelece uma **regra de contingência**: caso um snapshot não permita retornos mensais consistentes para todas as séries/janelas do recorte requerido, o conjunto de métricas é reduzido a um subconjunto mínimo (sem “forçar” cálculos inconsistentes).

## 2.7 Controle de qualidade e rastreabilidade
O pacote congelado incorpora uma trilha de auditoria e evidências de controle de qualidade associadas ao status Gate02 PASS, incluindo verificações de consistência interna e procedimentos de validação. Adicionalmente, o protocolo pré-registrado inclui validação cruzada amostral com fonte alternativa como verificação de plausibilidade, sem substituir a fonte primária e sem alterar regras do desenho.

## 2.8 Nota de escopo (cautela mínima)
As escolhas de amostra operacional, estratégia buy-and-hold e benchmarks seguem o pré-registro e servem a um objetivo descritivo e reprodutível; limitações e implicações interpretativas devem ser consideradas na leitura.
