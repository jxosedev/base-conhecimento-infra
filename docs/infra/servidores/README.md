---
title: Servidores
description: Documentacao tecnica dos servidores da infraestrutura
---

# :material-server: Servidores

!!! info "Indice de Servidores"
    Documentacao tecnica completa de cada servidor: hardware, SO, servicos, backups e acesso.

---

## Resumo

| Status | SO | Producao | Dev |
|--------|-----|----------|-----|
| **7** ativos | Ubuntu 22.04 | **6** | **1** |

---

## Lista de Servidores

| Hostname | Ambiente | IP | SO | Uplink |
|----------|----------|----|-----|--------|
| [webapp-prod-01](webapp-prod-01.md) | Producao | `10.10.1.50` | Ubuntu 22.04 | 2x 1G |
| [webapp-prod-02](webapp-prod-02.md) | Producao | `10.10.1.51` | Ubuntu 22.04 | 2x 1G |
| [db-master-01](db-master-01.md) | Producao | `10.10.2.10` | Ubuntu 22.04 | 2x 10G |
| [db-replica-01](db-replica-01.md) | Producao | `10.10.2.11` | Ubuntu 22.04 | 2x 10G |
| [ci-runner-01](ci-runner-01.md) | Dev | `10.10.3.20` | Ubuntu 22.04 | 1x 1G |
| [monitor-01](monitor-01.md) | Producao | `10.10.4.5` | Ubuntu 22.04 | 1x 1G |
| [jump-prod-01](jump-prod-01.md) | Producao | `10.10.0.5` | Ubuntu 22.04 | 1x 1G |

---

## :material-content-save: Backups

| Servidor | Tipo | Frequencia | Destino |
|----------|------|------------|---------|
| webapp-* | DB dump | Diario 02h | S3 |
| db-* | pg_dump + WAL | Diario + Continuo | S3 |
| monitor-01 | Config | Semanal | Git |

---

## :material-tools: Como criar documentacao de um novo servidor

!!! tip "Use o template"
    1. Copie o arquivo `docs/assets/templates/template-a-servidor.md`
    2. Salve como `docs/infra/servidores/NOME-SERVIDOR.md`
    3. Preencha todos os campos
    4. Adicione a linha na tabela acima
    5. Abra um PR
