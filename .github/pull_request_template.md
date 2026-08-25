---
name: "Pull Request - Nova Documentacao"
about: "Adicionar ou atualizar documentacao na base de conhecimento"
title: "[DOC] "
labels: documentation
assignees: ""
---

## Descricao

<!-- Descreva brevemente o que esta sendo adicionado ou alterado -->

**Tipo de documento:**
<!-- Marque com [x] o que se aplica -->

- [ ] Servidor (documentacao tecnica)
- [ ] Runbook (resposta a incidentes)
- [ ] POP (procedimento operacional padrao)
- [ ] Politica
- [ ] Runbook de manutencao
- [ ] Correcao de erro / dados desatualizados
- [ ] Outro: ____________

**Secao afetada:**
<!-- Ex: infra/servidores/, runbooks/incidentes/, pop/ -->

---

## Checklist de Contribution

<!-- Marque com [x] quando aplicavel -->

### Conteudo

- [ ] titulo claro e descritivo
- [ ] descricao no frontmatter preenchida
- [ ] tags relevantes adicionadas
- [ ] blocos de admonition usados corretamente (`!!! note`, `!!! warning`, etc.)
- [ ] tabelas formatadas corretamente
- [ ] links internos funcionando (sem `[links quebrados]`)
- [ ] comandos testados ou verificados
- [ ] nenhuma senha/token/credencial exposta

### Formatacao

- [ ] indentacao consistente (4 espacos)
- [ ] linguagem indicada nos blocos de codigo (` ```bash `, ` ```yaml `, etc.)
- [ ] tabelas com cabecalho
- [ ] sem linhas em branco excessivas

### Seguranca

- [ ] **NENHUMA** senha, token ou chave privada no documento
- [ ] IPs internos sao genericos ou ficticios (10.x.x.x)
- [ ] nomes de usuarios sao genericos (usuario@empresa.com)
- [ ] dados sensiveis mascarados

---

## Conteudo Adicionado/Alterado

<!-- Cole aqui o markdown que esta sendo adicionado, ou descreva as alteracoes -->

```markdown
<!-- Conteudo aqui -->
```

---

## Prints / Evidencias (opcional)

<!-- Se aplicavel, anexe prints do site apos a alteracao -->

---

## Observacoes

<!-- Qualquer informacao adicional para o reviewer -->

---

<!-- 
## Como contribution:

1. Fork o repo ou crie uma branch
2. Copie o template correspondente de docs/assets/templates/
3. Preencha o conteudo
4. Teste localmente: mkdocs serve
5. Abra este PR com a descricao acima
6. Aguarde revisao de pelo menos 1 membro do time
-->
