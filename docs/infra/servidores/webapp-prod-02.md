---
title: webapp-prod-02
description: Servidor de aplicação web - Produção 02
---

# webapp-prod-02

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `webapp-prod-02` |
| **IP** | `10.10.1.51` |
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
ssh ubuntu@10.10.1.51
ssh -J ubuntu@10.10.0.5 ubuntu@10.10.1.51
```

---

## Backups

| Tipo | Frequência | Retenção | Destino |
|------|------------|----------|---------|
| Database dump | Diário 02h | 30 dias | S3 |
| Config files | Semanal | 90 dias | Git |

---

## Ver Também

- [Lista de Servidores](README.md)
