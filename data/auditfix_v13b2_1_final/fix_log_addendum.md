# Fix Log — Addendum (v13b2.1-final)

Este adendo atualiza a interpretação do `fix_log.md` (rodada intermediária) para refletir o estado final do bundle.

1. **Dupla extração mensal (IND) concluída (estado final).**
   - Método A: pdfplumber.
   - Método B: PyMuPDF/fitz (extração por palavras/coordenação).
   - Resultado: 0 divergências mês-a-mês no conjunto auditado (ver `diff_full_T2_monthly.csv`).

2. **Overlap entre janelas (diagnóstico).**
   - O arquivo `overlap_report.csv` reporta mismatches entre janelas e 25Y como diagnóstico.
   - Para Portfólios A/B/C, mismatches são esperados por construção (janelas independentes; pesos iguais no início; buy-and-hold sem rebalanceamento).
