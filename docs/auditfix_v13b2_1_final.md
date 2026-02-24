---
# v13b2.1-final — Auditoria e correção PDF→planilha (Mais Retorno)

## Escopo
Esta atualização substitui os datasets derivados anteriores por uma versão auditada e corrigida a partir dos relatórios PDF do provedor (Mais Retorno). O desenho do estudo (janelas, snapshots, definições operacionais e métricas) permanece inalterado; foram corrigidas apenas discrepâncias na extração/transcrição e no cálculo de métricas derivadas.

## Fonte canônica (decisão operacional)
- **Tabela 1 (T1 — Total Return/CAGR):** valores canônicos extraídos dos relatórios **CMP**.
- **Tabela 2 (T2 — Risco):** métricas recalculadas a partir dos retornos mensais “Rentabilidade Histórica” dos relatórios **IND**, **por janela** (cada janela usa seu próprio PDF IND).  
  Observação: para Portfólios A/B/C, janelas são experimentos independentes (pesos iguais no início; buy-and-hold sem rebalanceamento), portanto meses de calendário sobrepostos entre janelas podem divergir por construção. O arquivo `overlap_report.csv` é mantido como **diagnóstico**.

## Arquivos canônicos a partir deste commit (usar SOMENTE estes)
Diretório: `data/auditfix_v13b2_1_final/`
- `T1_total_return_CAGR_v13b2.csv`
- `T2_risk_core_v13b3.csv`
- `T3_robust_total_return_CAGR_v13b2.csv`
- `T3_robust_portfolio_ranking_v13b2.csv`

## Artefatos de auditoria / QA (rastro auditável)
- `QA_GATE_FINAL.md` — gates e contagens finais
- `fix_log.md` — registro de correções e decisões
- `diff_full_T2_monthly.csv` — verificação mês-a-mês (dupla extração) para T2
- `overlap_report.csv` — diagnóstico de sobreposição entre janelas
- `CHECKSUMS_SHA256.txt` — hashes de integridade
- `MANIFEST_FINAL.md` — lista de arquivos e descrição do bundle

## Planilhas usadas no paper (saída editorial)
Diretório: `paper/tables/final/`
- `Tabela_1.xlsx`
- `Tabela_2.xlsx`
- `Tabela_3_painel_A.xlsx`
- `Tabela_3_painel_B.xlsx`

Essas planilhas devem ser consistentes com os CSVs canônicos e são destinadas a montagem/colagem no manuscrito.

## O que mudou (resumo)
- Correção de discrepâncias pontuais em T1 detectadas na auditoria (CMP).
- Recomputação de T2 a partir dos mensais IND por janela, com QA estruturado.
- Regeneração de T3 a partir de T1 canônica.

## O que NÃO mudou
- Desenho do estudo e framing (observacional; sem inferência; sem recomendação).
- Definições operacionais de janelas/snapshots/carteiras.
- PDFs originais não redistribuídos (restrições de licenciamento).

---
