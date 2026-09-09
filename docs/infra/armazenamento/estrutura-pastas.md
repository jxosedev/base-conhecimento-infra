---
title: Estrutura de Pastas
description: Organizacao padrao de diretorios em storage compartilhado
---

# :material-folder-network: Estrutura de Pastas

!!! info "Storage Compartilhado"
    Organizacao padrao dos diretorios no NAS e nos compartilhamentos de rede.

---

## Arvore de Diretorios

```text
/storage
├── /departamentos      # Pastas por area (RH, Financeiro, TI...)
├── /projetos           # Arquivos de projetos ativos
├── /publico            # Leitura para todos os colaboradores
├── /backups            # Destino de backups locais (ver runbooks)
└── /temp               # Arquivos temporarios (limpeza automatica 30d)
```

---

## Convencoes de Nomenclatura

- Usar `kebab-case` para nomes de pastas: `projeto-novo-site`
- Evitar acentos e caracteres especiais
- Prefixar por ano em pastas de projeto: `2026-migracao-erp`

---

## Permissoes

| Diretorio | Acesso | Grupo |
|-----------|--------|-------|
| `/departamentos/<area>` | Leitura/Escrita | Grupo da area |
| `/publico` | Leitura | Todos |
| `/backups` | Restrito | `infra` |
| `/temp` | Leitura/Escrita | Todos (expira em 30d) |

!!! warning "Dados sensiveis"
    Nunca armazenar credenciais, chaves privadas ou dados pessoais fora dos
    cofres apropriados. Ver [Politica de Seguranca](../../politicas/seguranca.md).

---

## Ver Tambem

- [Ferramentas de Backup](ferramentas-backup.md)
- [Politica de Backup](../../politicas/backup.md)
