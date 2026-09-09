---
title: monitor-01
description: Servidor de monitoramento
---

# monitor-01

## Informações Gerais

| Campo | Valor |
|-------|-------|
| **Hostname** | `monitor-01` |
| **IP** | `10.10.4.5` |
| **Ambiente** | Produção |
| **SO** | Ubuntu 22.04 LTS |
| **Hardware** | Dell PowerEdge R440 |
| **Status** | :material-check-circle: Ativo |

---

## Especificações

| Recurso | Valor |
|---------|-------|
| CPU | 1x Intel Xeon Silver 4214 (12C/24T) |
| RAM | 32GB DDR4 |
| Disco | 2x 960GB SSD RAID 1 |
| Rede | 1x 1Gbps |

---

## Serviços

| Serviço | Porta | Status |
|---------|-------|--------|
| Zabbix Server | 10051 | :material-check-circle: Rodando |
| Grafana | 3000 | :material-check-circle: Rodando |
| Prometheus | 9090 | :material-check-circle: Rodando |

---

## Acesso

```bash
ssh ubuntu@10.10.4.5
# Grafana: http://10.10.4.5:3000
```

---

## Ver Também

- [Lista de Servidores](README.md)
