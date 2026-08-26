---
title: jump-prod-01
description: Servidor Jump Host de Produção
---

# jump-prod-01

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `jump-prod-01` |
| **IP** | `10.10.0.5` |
| **Ambiente** | Produção |
| **SO** | Ubuntu 22.04 LTS |
| **Hardware** | Dell PowerEdge R440 |
| **Status** | :material-check-circle: Ativo |

---

## Especificações

| Recurso | Valor |
|---------|-------|
| CPU | 1x Intel Xeon Silver 4210 (10C/20T) |
| RAM | 16GB DDR4 |
| Disco | 2x 240GB SSD RAID 1 |
| Rede | 1x 1Gbps |

---

## Serviços

| Serviço | Porta | Status |
|---------|-------|--------|
| SSH | 22 | :material-check-circle: Rodando |
| Guacamole | 8080 | :material-check-circle: Rodando |

---

## Acesso

```bash
# Acesso direto
ssh ubuntu@10.10.0.5

# Via Guacamole Web
http://10.10.0.5:8080
```

---

## Servidores Acessíveis via Jump

| Hostname | IP | Comando |
|----------|-----|---------|
| webapp-prod-01 | 10.10.1.50 | `ssh -J ubuntu@10.10.0.5 ubuntu@10.10.1.50` |
| webapp-prod-02 | 10.10.1.51 | `ssh -J ubuntu@10.10.0.5 ubuntu@10.10.1.51` |
| db-master-01 | 10.10.2.10 | `ssh -J ubuntu@10.10.0.5 ubuntu@10.10.2.10` |
| db-replica-01 | 10.10.2.11 | `ssh -J ubuntu@10.10.0.5 ubuntu@10.10.2.11` |

---

## Ver Também

- [Lista de Servidores](../README.md)
