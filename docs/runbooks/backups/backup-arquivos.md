---
title: Backup de Arquivos
description: Runback para backup de arquivos criticos
---

# Backup de Arquivos

## Frequencia

Diario

---

## Procedimento

### Backup com rsync

```bash
rsync -avz --delete /origem/ /backup/destino/
```

### Backup com tar

```bash
tar -czf /backup/arquivos_$(date +%Y%m%d).tar.gz /caminho/arquivos/
```

### Backup para S3

```bash
aws s3 sync /backup/ s3://meu-bucket/backup/ --delete
```

---

## Verificacao

```bash
# Verificar tamanho
du -sh /backup/*

# Testar integridade
tar -tzf /backup/arquivos_*.tar.gz | head
```

---

## Ver Tambem

- [Backup de Banco](backup-banco.md)
- [Verificacao de Backup](verificacao.md)
