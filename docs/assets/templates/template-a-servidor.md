---
title: "Servidor — [NOME_DO_SERVIDOR]"
description: "Documentação técnica completa do servidor."
tags: [infra, servidores, documentacao]
---

# Servidor — `webapp-prod-01`

!!! info "Resumo Rápido"
    | Campo          | Valor                  |
    |----------------|------------------------|
    | **Ambiente**   | Produção               |
    | **IP**         | 10.10.1.50             |
    | **Hostname**   | webapp-prod-01         |
    | **Status**     | :material-check-circle: Ativo |
    | **Responsável**| Time de Infraestrutura |

---

## 1. Especificações de Hardware

!!! example "Recursos Físicos"
    - **CPU:** 8 vCPU (Intel Xeon Gold 6248R @ 3.0GHz)
    - **RAM:** 32 GB DDR4 ECC
    - **Disco:** 500 GB NVMe SSD (sistema) + 2 TB SATA (dados)
    - **Rede:** 2x 10 Gbps (bond0 - LACP)
    - **Serial:** `SN-2024-XXXXXX`

---

## 2. Sistema Operacional

!!! abstract "SO e Kernel"
    - **Distribuição:** Ubuntu 22.04.4 LTS (Jammy Jellyfish)
    - **Kernel:** 5.15.0-91-generic
    - **Arquitetura:** amd64
    - **Último update:** 2026-08-10
    - **Gerenciamento de pacotes:** apt

---

## 3. Serviços Instalados

!!! tip "Serviços Ativos"
    | Serviço       | Versão | Porta | Status       |
    |---------------|--------|-------|--------------|
    | nginx         | 1.24.0 | 80,443| `active`     |
    | postgresql    | 15.4   | 5432  | `active`     |
    | redis-server  | 7.2.3  | 6379  | `active`     |
    | docker-ce     | 24.0.7 | —     | `active`     |

!!! warning "Serviços Desativados"
    - `telnet.service` — desativado por política de segurança
    - `ftp.service` — desativado (usar SFTP)

---

## 4. Monitoramento e Alertas

!!! note "Ferramentas de Monitoramento"
    - **Métricas:** Prometheus + Grafana (dashboard: `http://grafana.internal/d/webapp-01`)
    - **Logs:** Loki + Promtail (stack ELK para logs históricos)
    - **Uptime:** UptimeRobot / Blackbox Exporter
    - **Alertas:** Canais Slack `#infra-alertas` e e-mail `infra@empresa.com`

!!! danger "Limites de Alerta"
    - CPU > 90% por 5 min → **Crítico**
    - RAM > 85%持续 → **Warning**
    - Disco > 80% → **Warning**
    - Disco > 90% → **Crítico**
    - Latência API > 500ms → **Warning**

---

## 5. Backup e Restauração

!!! warning "Política de Backup"
    - **Ferramenta:** Restic + cron + S3 (MinIO)
    - **Frequência:** Diário às 02:00 (full) / 6 em 6 horas (incremental)
    - **Retenção:** 30 diários, 12 semanais, 6 mensais
    - **Local:** S3 `s3://backups-infra/webapp-prod-01/`
    - **Último backup:** Verificar `cron` ou painel Grafana

!!! example "Comando de Restauração"
    ```bash
    # Listar snapshots disponíveis
    restic -r s3:s3.amazonaws.com/backups-infra/webapp-prod-01 snapshots

    # Restaurar para diretório temporário
    restic -r s3:s3.amazonaws.com/backups-infra/webapp-prod-01 restore latest --target /tmp/restore

    # Restaurar banco PostgreSQL específico
    restic -r s3:s3.amazonaws.com/backups-infra/webapp-prod-01 restore latest --target /tmp/restore --include "pgsql/"
    ```

---

## 6. Contas e Acesso

!!! danger "Acesso Remoto"
    - **SSH:** `ssh admin@10.10.1.50` (chave SSH certificada — sem senha)
    - **Jump Host:** `jump.intranet` → `10.10.1.50`
    - **VPN:** WireGuard — peer `infra-prod-01`
    - **Painel:** `https://zabbix.empresa.com/host.php?hostid=12345`

!!! warning "Regras de Acesso"
    - Acesso SSH requer aprovação do líder de infra
    - Credenciais armazenadas em **HashiCorp Vault** (engine: `infra/prod`)
    - Revogar acesso imediatamente ao desligar funcionário

---

## 7. Plano de Contingência

!!! abstract "Failover e DR"
    - **Alta disponibilidade:** Cluster com `webapp-prod-02` (10.10.1.51)
    - **Load Balancer:** HAProxy (keepalived + VRRP)
    - **RTO:** 15 minutos
    - **RPO:** 6 horas (último backup consistente)
    - **Procedimento de failover:** Ver `runbook-failover.md`

---

## 8. Histórico de Mudanças

| Data       | Responsável  | Descrição                                    |
|------------|--------------|----------------------------------------------|
| 2026-08-10 | João Silva   | Atualização kernel 5.15.0-91-generic          |
| 2026-07-22 | Maria Costa  | Expansão disco de 1TB para 2TB               |
| 2026-06-15 | Pedro Lima   | Migração de NFS para EFS                     |

---

!!! tip "Documentação Atualizada"
    Última atualização: `2026-08-25` | Autor: Time de Infraestrutura
