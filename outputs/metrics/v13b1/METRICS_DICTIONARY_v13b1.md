# Apêndice — Dicionário de Métricas (v13b1)

**Fonte (citar em texto/figura):** *Dados: Mais Retorno (relatórios PDF exportados) — bundle v13b1 — Gate02 PASS.*

Este apêndice define, **sem ambiguidade**, como cada métrica é calculada no estudo a partir do material congelado do **bundle v13b1**.

---

## 1) Estruturas de dados usadas (bundle v13b1)

### 1.1 `MONTHLY_LONG` (série mensal derivada do snapshot)
Campos relevantes:
- `cut` ∈ {`D0`, `D6M`, `D12M`}
- `window` ∈ {`5Y`,`10Y`,`15Y`,`20Y`,`25Y`}
- `series` ∈ {`PA`,`PB`,`PC`,`CDI`,`IBOV`,`SP500_PR`,`SP500_TR`}
- `date` (timestamp do mês; convenção do arquivo: primeiro dia do mês como rótulo do mês)
- `ret` (retorno mensal em decimal)
- `index` (nível mensal acumulado, **base 100** no início da janela)
- `report_id` (identificador único por cut×window×series)

> A série mensal é usada para **métricas de risco**, meses negativos, pior mês e drawdown.

### 1.2 `RAW_METRICS` (métricas canônicas do PDF + rastreabilidade)
Campos relevantes:
- `start_date`, `end_date` (datas do PDF)
- `years` = (end_date − start_date) / 365,25
- `total_return` (rentabilidade acumulada do PDF; **métrica primária canônica**)
- `cagr` (CAGR do PDF; usado como canônico)
- `md5` (hash MD5 do PDF do `report_id`)

> `total_return` e `cagr` são tratados como **canônicos do PDF** para evitar divergência de arredondamento ao encadear retornos mensais.

---

## 2) Notação

Para um dado `report_id` (fixa `cut`, `window`, `series`):

- Retornos mensais: \( r_t \) (coluna `ret`), em decimal.
- Série de nível mensal: \( I_t \) (coluna `index`), base 100 no início.
- Número de observações mensais: \( N \) (contagem de linhas na `MONTHLY_LONG` do report_id).
- CDI mensal (mesmo `cut` e `window`): \( r^{CDI}_t \).

---

## 3) Métricas (definições formais)

### 3.1 Retorno total acumulado (métrica primária — canônica do PDF)
\[
TR = \texttt{total\_return (RAW\_METRICS)}
\]

Unidade: decimal (ex.: 1,50 = +150%).

> A planilha também expõe `total_return_recalc_from_monthly_index = I_T/100 - 1` apenas para transparência (não-canônico).

---

### 3.2 CAGR (canônico do PDF)
\[
\text{years} = \frac{(\text{end\_date} - \text{start\_date})}{365,25}
\]
\[
CAGR = \texttt{cagr (RAW\_METRICS)}
\]

> Interpretação equivalente: \( CAGR = (1+TR)^{1/years} - 1 \).

---

### 3.3 Volatilidade anualizada (a partir de retornos mensais)
- Desvio padrão mensal **amostral** (n−1):
\[
\sigma_m = \text{stdev.S}(r_t)
\]
- Anualização:
\[
\sigma_a = \sigma_m\sqrt{12}
\]

---

### 3.4 Sharpe anualizado (excesso vs CDI, mensal → anual)
- Excesso mensal:
\[
e_t = r_t - r^{CDI}_t
\]
- Sharpe mensal:
\[
Sharpe_m = \frac{\text{mean}(e_t)}{\text{stdev.S}(e_t)}
\]
- Anualização:
\[
Sharpe_a = Sharpe_m\sqrt{12}
\]

Convenções:
- Para `CDI`: \( e_t = 0 \Rightarrow Sharpe_a = 0 \).

---

### 3.5 Sortino anualizado (excesso vs CDI; downside = std dos excessos negativos)
- Excesso mensal: \( e_t = r_t - r^{CDI}_t \)
- Conjunto de meses “downside”:
\[
\mathcal{N} = \{ t : e_t < 0 \}
\]
- Downside deviation (amostral, **apenas meses negativos**):
\[
DD_m = \text{stdev.S}(\{ e_t : t \in \mathcal{N} \})
\]
- Sortino mensal:
\[
Sortino_m = \frac{\text{mean}(e_t)}{DD_m}
\]
- Anualização:
\[
Sortino_a = Sortino_m\sqrt{12}
\]

Regras de borda:
- Se \(|\mathcal{N}| < 2\) (menos de 2 meses negativos), define-se `sortino_excess_cdi = 0`.

---

### 3.6 Máximo drawdown (mensal, pico-a-vale em `index`)
- Pico até t:
\[
P_t = \max_{k \le t} I_k
\]
- Drawdown no mês t:
\[
dd_t = \frac{I_t}{P_t} - 1
\]
- Máximo drawdown:
\[
MaxDD = \min_t (dd_t)
\]

---

### 3.7 % de meses negativos
\[
\%Neg = \frac{\#\{t: r_t < 0\}}{N}
\]

---

### 3.8 Pior mês / melhor mês
\[
Worst = \min_t(r_t), \quad Best = \max_t(r_t)
\]

---

## 4) Mapeamento de séries (`series`)
- `PA` = Portfólio A (TR)
- `PB` = Portfólio B (TR)
- `PC` = Portfólio C (TR)
- `CDI` = CDI (TR)
- `IBOV` = Ibovespa (TR)
- `SP500_PR` = S&P 500 em BRL (Price Return)
- `SP500_TR` = S&P 500 em BRL (Total Return)

---

## 5) Observação crítica (arredondamento)
O bundle v13b1 expõe, por transparência, a diferença absoluta:
- `total_return_abs_diff` = | total_return (PDF) − (index_final/100 − 1) |

Isso ocorre por limitações de arredondamento/representação dos retornos mensais no pipeline; **a métrica primária oficial é sempre a do PDF (RAW_METRICS)**.

