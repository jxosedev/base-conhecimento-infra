---
title: webapp-prod-01
description: Documentacao do servidor de aplicacao web em producao
tags: [servidor, producao, ubuntu, nginx]
---

# Servidor — `webapp-prod-01`

!!! info "Resumo Rapido"
    | Campo          | Valor                  |
    |----------------|------------------------|
    | **Ambiente**   | Producao               |
    | **IP**         | 10.10.1.50             |
    | **Hostname**   | webapp-prod-01         |
    | **Status**     | :material-check-circle: Ativo |
    | **Responsavel**| Time de Infraestrutura |

---

## 1. Especificacoes de Hardware

!!! example "Recursos Fisicos"
    - **CPU:** 8 vCPU (Intel Xeon Gold 6248R @ 3.0GHz)
    - **RAM:** 32 GB DDR4 ECC
    - **Disco:** 500 GB NVMe SSD (sistema) + 2 TB SATA (dados)
    - **Rede:** 2x 10 Gbps (bond0 - LACP)
    - **Serial:** `SN-2024-XXXXXX`

---

## 2. Sistema Operacional

!!! abstract "SO e Kernel"
    - **Distribuicao:** Ubuntu 22.04.4 LTS (Jammy Jellyfish)
    - **Kernel:** 5.15.0-91-generic
    - **Arquitetura:** amd64
    - **Ultimo update:** 2026-08-10

---

## 3. Servicos Instalados

!!! tip "Servicos Ativos"
    | Servico       | Versao | Porta | Status       |
    |---------------|--------|-------|--------------|
    | nginx         | 1.24.0 | 80,443| `active`     |
    | postgresql    | 15.4   | 5432  | `active`     |
    | redis-server  | 7.2.3  | 6379  | `active`     |
    | docker-ce     | 24.0.7 | —     | `active`     |

---

## 4. Monitoramento

!!! note "Ferramentas"
    - **Metricas:** Prometheus + Grafana
    - **Logs:** Loki + Promtail
    - **Uptime:** UptimeRobot
    - **Alertas:** Slack `#infra-alertas`

---

## 5. Backup

!!! warning "Politica de Backup"
    - **Ferramenta:** Restic + cron + S3
    - **Frequencia:** Diario as 02:00
    - **Retencao:** 30 diarios, 12 semanais, 6 mensais

---

## 6. Acesso

!!! danger "Credenciais"
    - **SSH:** `ssh admin@10.10.1.50`
    - **Jump Host:** `jump.intranet`
    - **VPN:** WireGuard peer `infra-prod-01`

---

!!! tip "Atualizado em 2026-08-25 | Time de Infraestrutura"
