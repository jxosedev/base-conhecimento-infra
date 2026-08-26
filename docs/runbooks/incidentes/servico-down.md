---
title: Servico Down
description: Runbook para servicos indisponiveis
---

# Servico Down

## Sintomas

- Servico retorna erro 5xx
- Servico nao responde
- Healthcheck falhando

---

## Diagnostico Rapido

### 1. Verificar status do servico

```bash
systemctl status <servico>
docker ps
pm2 list
```

### 2. Verificar portas

```bash
ss -tlnp | grep <porta>
netstat -tlnp | grep <porta>
```

### 3. Verificar logs

```bash
journalctl -u <servico> -f
tail -f /var/log/<servico>/*.log
```

---

## Fluxo de Resolucao

```mermaid
graph TD
    A[Servico Down] --> B{Processo rodando?}
    B -->|Sim| C{Porta aberta?}
    B -->|Nao| D[Reiniciar servico]
    C -->|Sim| E[Verificar upstream]
    C -->|Nao| F[Verificar config]
    D --> G[Verificar logs]
    E --> H[Verificar Nginx/LB]
    F --> I[Corrigir configuracao]
```

---

## Ver Tambem

- [Queda de Link](queda-link.md)
- [Lentidao de Rede](lentidao-rede.md)
