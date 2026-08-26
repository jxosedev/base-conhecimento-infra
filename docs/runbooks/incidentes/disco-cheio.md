---
title: Disco Cheio
description: Runbook para liberacao de espaco em disco
---

# Disco Cheio

## Sintomas

- Alerta de espaco em disco
- Servicos falhando
- Impossivel gravar logs

---

## Diagnostico Rapido

### 1. Verificar espaco

```bash
df -h
du -sh /* | sort -rh | head -20
```

### 2. Identificar maiores arquivos

```bash
find / -type f -size +100M -exec ls -lh {} \; 2>/dev/null
```

### 3. Verificar logs antigos

```bash
ls -lh /var/log/*.gz
journalctl --disk-usage
```

---

## Acoes de Emergencia

| Acao | Comando | Risco |
|------|---------|-------|
| Limpar logs | `journalctl --vacuum-size=100M` | Baixo |
| Limpar apt cache | `apt-get clean` | Baixo |
| Remover logs antigos | `rm /var/log/*.gz` | Baixo |
| Limpar Docker | `docker system prune -a` | Medio |

---

## Ver Tambem

- [Servico Down](servico-down.md)
