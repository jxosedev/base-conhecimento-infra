---
title: Primeiros Passos
description: Como comecar a usar a base de conhecimento
---

# Primeiros Passos

!!! info "Para novos usuarios"
    Guia rapido para navegar e encontrar o que voce precisa na base de conhecimento.

---

## Navegacao

- **Barra lateral esquerda**: Indice completo do conteudo
- **Barra superior**: Navegacao por secoes principais
- **Busca (Ctrl+K)**: Pesquisa full-text em todo o conteudo
- **Tema claro/escuro**: Alterne no icone de sol/lua no topo

---

## Como usar os templates

!!! tip "Templates disponiveis"
    Cada secao da infraestrutura segue um padrao. Ao criar nova documentacao:

    1. Copie o template mais proximo da pasta `docs/templates/`
    2. Renomeie para o nome do servidor/procedimento
    3. Preencha os campos marcados com `[colchetes]`
    4. Abra um PR para revisao do time

---

## Formatacao

!!! example "Exemplos de blocos disponiveis"
    === "Admonition Info"
        ```markdown
        !!! info "Titulo"
            Conteudo do bloco
        ```

    === "Admonition Warning"
        ```markdown
        !!! warning "Titulo"
            Conteudo de alerta
        ```

    === "Tabela"
        ```markdown
        | Coluna 1 | Coluna 2 |
        |----------|----------|
        | Dado     | Dado     |
        ```

    === "Codigo"
        ```markdown
        ```bash
        comando --aqui
        ```
        ```
