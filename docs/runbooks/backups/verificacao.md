---
title: Verificacao de Backup
description: Runbook para verificacao de integridade de backups
---

# Verificacao de Backup

## Frequencia

Semanal

---

## Procedimento

### 1. Verificar existencia

```bash
ls -lh /backup/*.dump
ls -lh /backup/*.tar.gz
```

### 2. Testar integridade

```bash
# PostgreSQL
pg_restore --list /backup/<banco>.dump

# Tar
tar -tzf /backup/*.tar.gz > /dev/null
```

### 3. Testar restore em ambiente de dev

```bash
# Restaurar em banco de teste
pg_restore -U postgres -d <banco_teste> /backup/<banco>.dump
```

---

## Relatorio

| Item | Status |
|------|--------|
| Arquivos presentes | :material-check-circle: OK |
| Integridade verificada | :material-check-circle: OK |
| Restore testado | :material-check-circle: OK |

---

## Ver Tambem

- [Backup de Banco](backup-banco.md)
- [Restauracao](restauracao.md)
