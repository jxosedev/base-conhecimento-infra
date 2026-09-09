---
title: db-replica-01
description: Servidor de banco de dados réplica
---

# db-replica-01

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `db-replica-01` |
| **IP** | `10.10.2.11` |
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

## Replicação

| Mestre | IP | Status | Lag |
|--------|-----|--------|-----|
| db-master-01 | 10.10.2.10 | :material-check-circle: Sincronizado | <1ms |

---

## Acesso

```bash
ssh ubuntu@10.10.2.11
psql -h 10.10.2.11 -U postgres
```

---

## Ver Também

- [Lista de Servidores](README.md)
