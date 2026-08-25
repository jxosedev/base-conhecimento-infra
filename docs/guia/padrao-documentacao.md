---
title: Padrao de Documentacao
description: Padroes e convencoes usados na base de conhecimento
---

# Padrao de Documentacao

!!! abstract "Convencoes"
    Todos os documentos devem seguir estes padroes para manter consistencia.

---

## Frontmatter Obrigatorio

```yaml
---
title: "Nome do Documento"
description: "Descricao curta"
tags: [tag1, tag2, tag3]
---
```

---

## Admonitions Disponiveis

| Tipo | Uso |
|------|-----|
| `note` | Informacao complementar |
| `tip` | Dica ou recomendacao |
| `info` | Informacao geral importante |
| `warning` | Alerta de cuidado |
| `danger` | Risco de seguranca ou perda de dados |
| `example` | Exemplo pratico de uso |
| `abstract` | Resumo ou contexto |
| `question` | Pergunta frequente |
| `success` | Confirmacao de procedimento ok |
| `failure` | Erro ou resultado negativo |

---

## Blocos de Codigo

Sempre indicar a linguagem:

````markdown
```bash
comando --shell
```

```python
print("hello")
```

```yaml
chave: valor
```
````

---

## Tabelas

```markdown
| Coluna 1 | Coluna 2 | Coluna 3 |
|----------|----------|----------|
| Dado     | Dado     | Dado     |
```
