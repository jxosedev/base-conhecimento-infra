---
title: Limpeza de Disco
description: Runbook para liberacao de espaco em disco
---

# Limpeza de Disco

## Frequencia

Sob demanda (alerta de disco)

---

## Procedimento

### 1. Identificar maiores consumidores

```bash
du -sh /* | sort -rh | head -10
du -sh /var/* | sort -rh | head -10
```

### 2. Limpar seguidores

| Local | Comando | Risco |
|-------|---------|-------|
| Logs | `journalctl --vacuum-size=100M` | Baixo |
| apt cache | `apt-get clean` | Baixo |
| Docker | `docker system prune -a` | Medio |
| Temp | `rm -rf /tmp/*` | Baixo |

### 3. Verificar espaco

```bash
df -h
```

---

## Ver Tambem

- [Disco Cheio](../incidentes/disco-cheio.md)
