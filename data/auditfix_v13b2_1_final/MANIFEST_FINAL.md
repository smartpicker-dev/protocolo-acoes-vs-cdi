# MANIFEST — Bundle auditado (v13b2.1-final)

Este bundle consolida os datasets auditados para o paper “Ações vs CDI”.

## Arquivos canônicos
- T1_total_return_CAGR_v13b2.csv  (Total Return e CAGR; canônico = CMP)
- T2_risk_core_v13b3.csv          (Risco; canônico = IND por janela, recomputado dos retornos mensais)
- T3_robust_total_return_CAGR_v13b2.csv
- T3_robust_portfolio_ranking_v13b2.csv

## Artefatos de auditoria / QA
- QA_GATE_FINAL.md        (gate final; inclui verificação independente e explicita o uso de overlap como diagnóstico)
- diff_full_T2_monthly.csv (verificação independente pdfplumber vs PyMuPDF, mês-a-mês; esperado: 0 divergências)
- overlap_report.csv       (diagnóstico: mismatches entre janelas e 25Y; esperado para Portfólios A/B/C)
- fix_log.md               (histórico de correções da rodada intermediária)
- fix_log_addendum.md      (adendo alinhando o fix_log ao estado final do bundle)

## Convenção canônica adotada
A) Por janela canônico (IND de cada janela para T2). Overlap entre janelas é tratado como diagnóstico; 
para Portfólios A/B/C é esperado por construção (janelas independentes).
