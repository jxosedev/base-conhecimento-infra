---
title: Como Contribuir
description: Guia para adicionar e atualizar documentacao
---

# Como Contribuir

!!! tip "Contribuindo com a base"
    Toda documentacao esta versionada no GitHub. Para alteracoes, siga o fluxo abaixo.

---

## Fluxo de Alteracao

1. **Fork** ou crie uma branch a partir de `main`
2. Edite o arquivo `.md` desejado
3. Teste localmente com `mkdocs serve`
4. Abra um **Pull Request** com descricao da alteracao
5. Aguarde revisao de pelo menos 1 membro do time

---

## Padrao de Arquivos

!!! abstract "Nomenclatura"
    - **Servidores**: `docs/infra/servidores/NOME-SERVIDOR.md`
    - **Runbooks**: `docs/runbooks/categoria/NOME-RUNBOOK.md`
    - **POPs**: `docs/pop/NOME-PROCEDIMENTO.md`
    - **Politicas**: `docs/politicas/NOME-POLITICA.md`

!!! warning "Regras"
    - Sempre usar frontmatter com `title`, `description` e `tags`
    - Usar admonitions para informacoes importantes
    - Incluir datas de atualizacao no rodape
    - Nunca expor senhas, tokens ou credenciais
