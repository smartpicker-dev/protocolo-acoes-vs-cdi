# QA Gate Final — v13b2.1-final

## Escopo
- T1: validada por extração dos PDFs CMP (Total% e CAGR%).
- T2: recomputada a partir dos retornos mensais dos PDFs IND (por janela e snapshot), com validação independente mês-a-mês.
- T3: regenerada a partir de T1.

## Verificações

1) **Dupla extração independente (mensal, IND):** pdfplumber vs PyMuPDF/fitz. Resultado: 0 divergências (esperado = 0).
2) **Gate PR vs TR (T1 D-12m 25Y):** SP500_PR ≠ SP500_TR (Total e CAGR).
3) **Overlap entre janelas:** tratado como diagnóstico (não-gate) sob a convenção canônica por janela.

## Resultados

- `diff_full_T2_monthly.csv`: **0** linhas (0 = PASS).
- `overlap_report.csv`: Portfólios A/B/C apresentam mismatches extensivos (esperado por construção): PA=1808, PB=1811, PC=1808.
- Benchmarks apresentam 1 mismatch por janela (normalmente no primeiro mês da janela, convenção de início): total mismatches por benchmark = {'CDI': 12, 'IBOV': 12, 'SP500_PR': 12, 'SP500_TR': 12}.

## Status

PASS para T1/T2 sob a convenção canônica por janela, com validação independente dos mensais (diff=0). Overlap mantido como diagnóstico.
