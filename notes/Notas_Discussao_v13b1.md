# Notas — Discussão / Limitações / Conclusão (v13b1)

## 0\) Enquadramento editorial (trabalho publicável)

- **Natureza do trabalho:** estudo de caso histórico, reprodutível e auditável; **não** é recomendação e **não** implica garantia de retorno.  
- **Contribuição (obrigatório manter explícito em 3.1):**  
  - **Metodológica:** desenho reprodutível com janelas fixas \+ 3 snapshots pré-definidos \+ trilha de auditoria \+ bundle congelado (v13b1 / Gate02 PASS).  
  - **Aplicada ao contexto brasileiro:** documenta de forma auditável que o diferencial “ações vs CDI” é sensível ao **horizonte** e à **data final**, reconciliando leituras de curto vs longo prazo **sem inferir causalidade**.  
- **Regra de linguagem (evitar “defensivo demais”):**  
  - Preferir **descrição observacional** (“observa-se”, “nos recortes analisados”, “os resultados indicam”) e **limitar inferência** (“consistente com”, “mecanismo plausível”, “sem atribuição causal”).  
  - Evitar absolutos (“prova”, “garante”, “sempre”) e evitar termos que sugiram “alfa” estatístico.

## 1\) Fonte de dados e rastreabilidade (padrão único)

- **Fonte única para números:** exclusivamente Tabelas 1–3 e Figuras 1–4.  
- **Citação padrão (usar exatamente):**  
  - “Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS”.  
- **Padrão editorial (sem repetição por seção):**  
  - No corpo do Capítulo 3, **não** repetir “Dados e reprodutibilidade” em cada subseção.  
  - Manter **um único** parágrafo “Disponibilidade de dados e reprodutibilidade (Capítulo 3)” **no final do Capítulo 3**, incluindo:  
    - origem (PDFs exportados do Mais Retorno),  
    - bundle v13b1 \+ Gate02 PASS,  
    - referência aos outputs canônicos no pacote de replicação,  
    - observação de **restrição de licença** (não redistribuição dos PDFs), preservando o caminho de reprodução via IDs/manifestos/instruções.

## 2\) Padronização de termos (consistência interna)

- **Escolha única de grafia:** usar **buy-and-hold** (não alternar com “buy & hold”).  
- **Pesos e índices (evitar anglicismo de jargão):**  
  - usar “**ponderado por valor de mercado ajustado por free float**” (evitar “cap-weight”).  
  - usar “**pesos iguais (equal-weight) no início da janela**”.  
- **Benchmarks (coerência com figuras/manifesto):**  
  - CDI (benchmark primário).  
  - Ibovespa (TR).  
  - S\&P 500 em BRL: explicitar **PR** \= sem reinvestimento de proventos; **TR** \= com reinvestimento teórico; ambos em BRL **embutem câmbio BRL/USD**.  
- **Risco:** não confundir “risco” com “volatilidade” apenas; no texto, risco é reportado por **volatilidade e drawdown máximo** (e métricas de eficiência Sharpe/Sortino do excesso vs CDI).

## 3\) 3.1.1 — O que os resultados mostram (checagens e cautelas)

- **Não absolutizar:** manter “**em parte dos recortes de horizontes mais longos**” quando afirmar superação do CDI (coerente com Tabela 1/Tabela 3).  
- **Comparação risco–retorno:** ao afirmar retorno maior, **sempre** emparelhar com “risco materialmente maior” (volatilidade e drawdown) referenciando Tabela 2/Figuras 3a/3b.  
- **CDI drawdown \= 0 (evitar gatilho de revisor):**  
  - Redação correta: “na série acumulada do CDI utilizada neste snapshot, o índice é monotônico; por isso, o drawdown máximo medido pela métrica adotada é reportado como 0 na amostra”.  
  - Não generalizar como propriedade “intrínseca” do CDI fora da amostra/métrica.

## 4\) 3.1.2 — Mecanismos plausíveis (ancoragem mínima com literatura)

- **Regra:** (i)–(v) são **mecanismos potenciais, não causais**; evitar “porque são empresas melhores”.  
- **Ancoragem por item (mínimo publicável, sem mexer em dado):**  
  - (i) Regras de índice / elegibilidade / ponderação: citar metodologia oficial (B3, 2021; B3, 2023).  
  - (ii) Equal-weight vs valor de mercado \+ 1/N vs otimização: citar (DEMIGUEL; GARLAPPI; UPPAL, 2009).  
  - (iii) “Poucos vencedores” e assimetria de retornos no longo prazo: citar (BESSEMBINDER, 2018).  
  - (iv) Viés de sobrevivência/seleção: citar (ELTON; GRUBER; BLAKE, 1996).  
  - (v) Risco cambial em ativos internacionais: citar (ADLER; DUMAS, 1983).  
- **Gestão ativa:** uma frase basta: “não há decisões dinâmicas típicas de gestão ativa (rebalanceamento/rotação/timing)”.

## 5\) 3.1.3 — Robustez (anti-cherry-picking)

- **Snapshots e datas (usar exatamente):**  
  - D0 \= 10/02/2026; D-12m \= 10/02/2025; D-6m \= 08/08/2025 (ajuste por não-pregão; alvo 10/08/2025).  
- **Frase-âncora interpretativa (manter):**  
  - “isso limita inferências em janelas curtas e sugere que o diferencial ‘ações vs CDI’ depende criticamente do horizonte e da data final”.  
- **Exemplo específico (PB 5 anos no D-12m):**  
  - manter como **exemplo** de instabilidade em janelas curtas, sem soar “cherry”; preferir “há casos em que…” \+ exemplo.

## 6\) 3.2 — Limitações e ameaças à validade (sem redundância)

- **Validade interna:** meses parciais/anualização \+ ajuste D-6m \+ instabilidade 5 anos \+ dependência de séries mensais para risco (vol, Sharpe/Sortino, drawdown, % meses negativos).  
- **Validade externa:** fricções ignoradas; recorte não representativo; sobrevivência/seleção; rigidez do buy-and-hold (sem aportes/rotação/otimização).  
- **Validade de construto:** CDI como proxy operacional de risk-free; TR como reinvestimento teórico; proxy de risco incompleta (vol/drawdown não esgotam).  
- **Universo efetivo:** no corpo, usar apenas “**14 tickers (união A/B/C; ver Apêndice A)**”; evitar “parede de tickers” na discussão.

## 7\) 3.3 — Conclusão (forma acadêmica)

- **Manter**: “em parte dos recortes de horizontes longos” ao resumir superação do CDI.  
- **Manter**: robustez como qualificador (janelas curtas mais sensíveis; longas mais estáveis), sem eliminar limitações estruturais.  
- **Fecho:** reiterar “sem inferir causalidade” e “sem recomendação”.

