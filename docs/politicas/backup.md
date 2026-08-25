---
title: Politica de Backup
description: Diretrizes de backup e retencao de dados
tags: [politica, backup, retencao]
---

# Politica de Backup

!!! warning "Obrigatorio"
    Todos os servidores criticos devem ter backup configurado conforme abaixo.

---

## Niveis de Backup

| Tipo | Frequencia | Retencao | Destino |
|------|------------|----------|---------|
| Full | Diario (02:00) | 30 dias | S3 + Local |
| Incremental | 6/6 horas | 7 dias | S3 |
| Semanal | Domingo | 12 semanas | S3 + Offsite |
| Mensal | Dia 1 | 12 meses | Offsite |

---

## Ferramentas

!!! tip "Stack de Backup"
    - **Arquivos:** Restic + S3 (MinIO)
    - **Banco de Dados:** pg_dump + WAL archiving
    - **Configuracao:** Ansible + cron
    - **Monitoramento:** Grafana dashboard

---

## Restauracao

!!! example "Comandos de restauracao"
    ```bash
    # Listar snapshots
    restic -r s3:s3.amazonaws.com/backups snapshots

    # Restaurar ultimo snapshot
    restic -r s3:s3.amazonaws.com/backups restore latest --target /tmp/restore
    ```
