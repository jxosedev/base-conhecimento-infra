---
title: webapp-prod-01
description: Servidor de aplicação web - Produção 01
---

# webapp-prod-01

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `webapp-prod-01` |
| **IP** | `10.10.1.50` |
| **Ambiente** | Produção |
| **SO** | Ubuntu 22.04 LTS |
| **Hardware** | Dell PowerEdge R740 |
| **Status** | :material-check-circle: Ativo |

---

## Especificações

| Recurso | Valor |
|---------|-------|
| CPU | 2x Intel Xeon Silver 4214 (12C/24T) |
| RAM | 64GB DDR4 |
| Disco | 2x 480GB SSD RAID 1 |
| Rede | 2x 1Gbps (bond0) |

---

## Serviços

| Serviço | Porta | Status |
|---------|-------|--------|
| Nginx | 80/443 | :material-check-circle: Rodando |
| Node.js | 3000 | :material-check-circle: Rodando |
| PM2 | - | :material-check-circle: Rodando |

---

## Acesso

```bash
# SSH
ssh ubuntu@10.10.1.50

# Via Jump Host
ssh -J ubuntu@10.10.0.5 ubuntu@10.10.1.50
```

---

## Backups

| Tipo | Frequência | Retenção | Destino |
|------|------------|----------|---------|
| Uploads / assets | Diário 02h | 30 dias | S3 |
| Config files | Semanal | 90 dias | Git |
| Snapshot VM | Semanal | 4 semanas | vSphere |

---

## Monitoramento

- **Zabbix:** Host `webapp-prod-01`
- **Grafana:** Dashboard `WebApp Production`
- **Logs:** `/var/log/nginx/`, PM2 logs

---

## Últimas Manutenções

| Data | Tipo | Descrição |
|------|------|-----------|
| 01/08/2026 | Atualização | Patch de segurança kernel |
| 15/07/2026 | Expansão | Upgrade RAM 32GB -> 64GB |

---

## Ver Também

- [Lista de Servidores](README.md)
- [Runbook de Incidentes](../../runbooks/incidentes/README.md)
