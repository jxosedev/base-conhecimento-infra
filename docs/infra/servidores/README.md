---
title: Servidores
description: Documentacao tecnica dos servidores da infraestrutura
---

# Servidores

!!! info "Indice de Servidores"
    Documentacao tecnica completa de cada servidor: hardware, SO, servicos, backups e acesso.

---

## Lista de Servidores

| Hostname | Ambiente | IP | SO | Status |
|----------|----------|----|-----|--------|
| [webapp-prod-01](webapp-prod-01.md) | Producao | 10.10.1.50 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [webapp-prod-02](webapp-prod-02.md) | Producao | 10.10.1.51 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [db-master-01](db-master-01.md) | Producao | 10.10.2.10 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [db-replica-01](db-replica-01.md) | Producao | 10.10.2.11 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [ci-runner-01](ci-runner-01.md) | Dev | 10.10.3.20 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [monitor-01](monitor-01.md) | Producao | 10.10.4.5 | Ubuntu 22.04 | :material-check-circle: Ativo |
| [jump-prod-01](jump-prod-01.md) | Producao | 10.10.0.5 | Ubuntu 22.04 | :material-check-circle: Ativo |

---

## Como criar documentacao de um novo servidor

!!! tip "Use o template"
    1. Copie o arquivo `docs/assets/templates/template-a-servidor.md`
    2. Salve como `docs/infra/servidores/NOME-SERVIDOR.md`
    3. Preencha todos os campos
    4. Adicione a linha na tabela acima
    5. Abra um PR
