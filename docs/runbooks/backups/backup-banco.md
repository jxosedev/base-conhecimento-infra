---
title: Backup de Banco
description: Runbook para backup de bancos de dados
---

# Backup de Banco

## Frequencia

Diario as 02h

---

## Procedimento

### Backup

```bash
# PostgreSQL
pg_dump -U postgres -d <banco> -F c -f /backup/<banco>_$(date +%Y%m%d).dump

# MySQL
mysqldump -u root -p <banco> > /backup/<banco>_$(date +%Y%m%d).sql
```

### Restauracao

```bash
# PostgreSQL
pg_restore -U postgres -d <banco> /backup/<banco>.dump

# MySQL
mysql -u root -p <banco> < /backup/<banco>.sql
```

---

## Verificacao

```bash
# Verificar integridade
pg_restore --list /backup/<banco>.dump
```

---

## Ver Tambem

- [Verificacao de Backup](verificacao.md)
- [Restauracao](restauracao.md)
