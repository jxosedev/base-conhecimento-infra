---
title: Restauracao
description: Runbook para restauracao de backups
---

# Restauracao

## Quando Usar

- Perda de dados
- Corrupcao de banco
- Rollback de change

---

## Procedimento

### 1. Identificar backup

```bash
ls -lh /backup/*.dump | tail -5
```

### 2. Restaurar

```bash
# PostgreSQL
pg_restore -U postgres -d <banco> /backup/<banco>.dump

# Arquivos
tar -xzf /backup/arquivos_*.tar.gz -C /
```

### 3. Verificar

```bash
# Conectar ao banco
psql -U postgres -d <banco>

# Contar registros
SELECT count(*) FROM <tabela>;
```

---

## Contatos

| Funcao | Contato |
|--------|---------|
| DBA | `(11) 9999-6666` |
| NOC | `(11) 3000-1000` |

---

## Ver Tambem

- [Backup de Banco](backup-banco.md)
- [Verificacao de Backup](verificacao.md)
