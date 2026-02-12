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

