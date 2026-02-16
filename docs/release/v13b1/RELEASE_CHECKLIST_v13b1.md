# Release checklist — v13b1

Este arquivo lista os artefatos “carimbados” no Git e os ponteiros OSF relevantes para o bundle v13b1.

## Regras (resumo)
- Git é o registro oficial de outputs leves (CSV/MD).
- XLSX é conveniência (pode ficar no Git); não espelhar no OSF por enquanto.
- OSF só será atualizado no release final (T1/T2/T3 + figuras + paper) para evitar trabalho duplicado.

## Ponteiros / Freezes
- DATA FREEZE pointer: `paper/DATA_FREEZE_REFERENCE.md`
- Tag do ponteiro do paper: `paper-data-freeze-v13b1-2026-02-16-132202-0300`
- Tag do README data-freeze (docs): `docs-data-freeze-v13b1-2026-02-16-133536-0300`
- Correção de placeholder 1016: `docs-data-freeze-v13b1-fix1016-2026-02-16-133840-0300`
- Índice de outputs no README: `docs-outputs-index-v13b1`

## Outputs v13b1 no Git

### Resultados (Agente 08)
- Pasta: `outputs/text/v13b1/`
- Tag: `results-v13b1`
- Arquivos: `Resultados_v13b1.md`, `Notas_Resultados_v13b1.md`

### Métricas (Agente 05)
- Pasta: `outputs/metrics/v13b1/`
- Tag: `metrics-v13b1`
- Arquivos: T1/T2 (+ wide), OFFICIAL_METRICS, RECOMPUTE_DIFFS, dicionário e build report.

### Robustez (Agente 06)
- Pasta: `outputs/robustness/v13b1/`
- Tag: `robustness-v13b1`
- Observação: T3 inclui colunas explícitas start/end dates (D0/D6M/D12M).
- Extras locais (não versionados): `outputs/robustness/v13b1/extras/` (ignorado no `.gitignore`).

### Figuras (Agente 07)
- Pasta: `outputs/figures/v13b1/`
- Commit: `b4166a2` (package + manifest)
- Tag: `figures-v13b1-2026-02-16-172039-0300`
- Observação: tags `figures-v13b1` / `figures-v13b1.1` já existiam antes; usar a tag com timestamp acima como referência desta entrega.

### Fontes de índices (IBOV / S&P 500)
- Pasta (Git): `paper/sources/indices/v13b1/`
- Tag: `sources-indices-v13b1`
- Ponteiro OSF (methods/indices freeze): `docs/methods/indices/v13b1/OSF_REFERENCE_methods-indices-v13b1.md`

## OSF (status atual)
- Gate02 PASS / data freeze principal: OSF registration `x2h9d` (project `q4vbz`) — já evidenciado no Git.
- Methods/indices: OSF registration `3rz9g` (associated project `ej5gf`) — ponteiro no Git.

## Faltando para o release final (placeholder)
- Paper final (T1/T2/T3 + texto + figuras finais integradas)
- Upload OSF do release final (pacote completo + checksums)
- Tag de release final (a definir)
