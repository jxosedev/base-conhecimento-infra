---
title: Ferramentas de Backup
description: Ferramentas utilizadas para backup e sincronizacao de dados
---

# :material-backup-restore: Ferramentas de Backup

!!! info "Ferramentas"
    Ferramentas padronizadas para backup, sincronizacao e verificacao de dados.

---

## Ferramentas Padronizadas

| Ferramenta | Uso | Onde |
|------------|-----|------|
| `pg_dump` / WAL-G | Backup de bancos PostgreSQL | db-* |
| `restic` | Backup incremental de arquivos | Servidores + NAS |
| `rsync` | Sincronizacao de arquivos | NAS -> S3/GCS |
| `aws s3 sync` | Envio de backups para S3 | Todos |

---

## Destinos

| Destino | Uso | Retencao |
|---------|-----|----------|
| S3 (`sa-east-1`) | Backups primarios offsite | 30-90 dias |
| NAS local | Copia rapida de restauracao | 14 dias |
| Glacier | Arquivamento de longo prazo | 1 ano+ |

---

## Boas Praticas

- [x] Backups criptografados em repouso (restic usa AES-256)
- [x] Verificacao periodica de integridade (ver runbook de verificacao)
- [x] Teste de restauracao trimestral
- [x] Segredos de backup guardados em Secret Manager

!!! tip "Runbooks relacionados"
    Os procedimentos passo a passo estao nos runbooks de backup.

---

## Ver Tambem

- [Estrutura de Pastas](estrutura-pastas.md)
- [Backup de Banco](../../runbooks/backups/backup-banco.md)
- [Backup de Arquivos](../../runbooks/backups/backup-arquivos.md)
- [Verificacao de Backups](../../runbooks/backups/verificacao.md)
- [Restauracao](../../runbooks/backups/restauracao.md)
