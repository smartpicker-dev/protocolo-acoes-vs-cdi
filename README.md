# Data freeze (fonte única)

Ponteiro canônico: `paper/DATA_FREEZE_REFERENCE.md`

Tag do ponteiro: `paper-data-freeze-v13b1-2026-02-16-132202-0300`

---

# Protocolo v1.0 — Ações vs CDI (pré-registro / freeze)

Este repositório registra o **protocolo (pré-registro)** de um estudo educacional reprodutível “Ações vs CDI”, incluindo:
- o texto do protocolo em Markdown (`PROTOCOLO_v1.0.md`)
- evidências em PDF (inclui versão assinada) em `evidence/`
- metadados do congelamento (`FREEZE_INFO.txt`)
- hashes SHA256 para verificação de integridade (`SHA256SUMS.txt`)
- manifesto do freeze com referências públicas (`FREEZE_MANIFEST.md`)

## Referências públicas (imutabilidade prática)
- Tag do freeze (conteúdo do protocolo): `freeze-2026-02-12-123649-0300`
- Commit do freeze: `dd2355c`
- Tag do manifest: `manifest-2026-02-12-123649-0300`
- Commit do manifest: `a32c2dd`

## Como verificar integridade (reprodutível)
1) Fazer checkout do freeze:
   `git checkout freeze-2026-02-12-123649-0300`

2) Verificar hashes:
   `shasum -a 256 -c SHA256SUMS.txt`

Saída esperada: todos os arquivos com status **OK**.

## Regra de mudanças
Qualquer alteração após o congelamento do v1.0 deve gerar **v1.1** com justificativa escrita (o que mudou, por quê e impacto esperado).

## Protocolo v1.1 (pré-coleta — auditabilidade)
- Tag (freeze): `protocol-v1.1`
- Commit (freeze): `b27ff3c`
- Manifest tag: `manifest-v1.1-2026-02-12-192949-0300`
- Manifest commit: `cccc9da`
- Arquivos: ver pasta `protocol/` (inclui PDF assinado + .md + .txt)
- Motivo: ver `protocol/CHANGELOG.txt`
- Verificação: `shasum -a 256 -c protocol/HASHES_v1.1_SHA256.txt`


## Protocolo v1.2 (pré-coleta — auditabilidade)
- Tag (freeze): protocol-v1.2
- Commit (freeze): 28598d9
- Manifest tag: manifest-v1.2-2026-02-12-205431-0300
- Manifest commit: dde6f6e
- Arquivos: ver pasta protocol/ (inclui PDF assinado + .md + .txt)
- Motivo: ver protocol/CHANGELOG.txt
- OSF prereg (842b7): `prereg-osf-842b7-v1.2-complete-2026-02-12-212044-0300` (commit `616273c`)
- Verificação: shasum -a 256 -c protocol/HASHES_v1.2_SHA256.txt

## Protocolo v1.3 (pré-coleta — auditabilidade)
- Tag (freeze): `protocol-v1.3`
- Commit (freeze): `6474cee`
- Manifest tag: `manifest-v1.3-2026-02-14-163458-0300`
- Manifest commit: `2d317d1`
- Natureza: errata editorial (sem impacto analítico)
- Motivo: ver `protocol/CHANGELOG.txt`
- OSF registro (8vub2): `prereg-osf-8vub2-v1.3-complete-2026-02-14-165200-0300` (commit `0b04860`)
- Verificação: `shasum -a 256 -c protocol/HASHES_v1.3_SHA256.txt`

## Gate 02 PASS — data freeze v13b1 (auditável/reprodutível)
- Commit (freeze): `dca78cb`
- Tag (freeze): `freeze-2026-02-15-1016-0300`
- Tag (gate02): `gate02-pass-v13b1-2026-02-15-105446-0300`
- Artefatos no Git: `docs/freeze/gate02/v13b1/`
  - Gate02_QA_Report_v13b.md
  - Gate02_PDF_to_Sheet_Audit_v13b.csv
  - pdf_manifest_v13b1.csv
  - CHECKSUMS_v13b1.txt
  - CHECKSUMS_freeze_2026-02-15-1016-0300.txt
  - README_FREEZE_gate02-pass_v13b1.md
- Binários no OSF (não versionados no Git):  
  - sources-methodology-maisretorno_v1.0_2026-02-15-1016-0300.zip  
  - study-data-freeze_gate02-pass_v13b1_2026-02-15-1016-0300.zip  
  - CHECKSUMS_freeze_2026-02-15-1016-0300.txt
- Verificação (Git, artefatos leves):
  `shasum -a 256 -c docs/freeze/gate02/v13b1/CHECKSUMS_freeze_2026-02-15-1016-0300.txt`

