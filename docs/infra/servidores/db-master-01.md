---
title: db-master-01
description: Servidor de banco de dados master
---

# db-master-01

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `db-master-01` |
| **IP** | `10.10.2.10` |
| **Ambiente** | Produção |
| **SO** | Ubuntu 22.04 LTS |
| **Hardware** | Dell PowerEdge R740xd |
| **Status** | :material-check-circle: Ativo |

---

## Especificações

| Recurso | Valor |
|---------|-------|
| CPU | 2x Intel Xeon Gold 5218 (16C/32T) |
| RAM | 128GB DDR4 |
| Disco | 4x 960GB SSD RAID 10 |
| Rede | 2x 10Gbps (bond0) |

---

## Serviços

| Serviço | Porta | Status |
|---------|-------|--------|
| PostgreSQL 15 | 5432 | :material-check-circle: Rodando |
| PgBouncer | 6432 | :material-check-circle: Rodando |

---

## Acesso

```bash
ssh ubuntu@10.10.2.10
psql -h 10.10.2.10 -U postgres
```

---

## Replicação

| Replica | IP | Status |
|---------|-----|--------|
| db-replica-01 | 10.10.2.11 | :material-check-circle: Sincronizado |

---

## Backups

| Tipo | Frequência | Retenção | Destino |
|------|------------|----------|---------|
| pg_dump | Diário 01h | 30 dias | S3 |
| WAL archive | Contínuo | 7 dias | S3 |
| Snapshot | Semanal | 4 semanas | vSphere |

---

## Ver Também

- [Lista de Servidores](../README.md)
