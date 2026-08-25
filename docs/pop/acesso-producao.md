---
title: POP — Acesso a Producao
description: Procedimento para solicitacao de acesso a ambientes de producao
tags: [pop, producao, seguranca]
---

# POP — Acesso a Producao

!!! danger "Acesso Restrito"
    Acesso a producao requer aprovacao formal. Nao existe acesso sem registro.

---

## Fluxo de Solicitacao

1. Funcionario solicita via Jira (template: `Solicitacao Acesso Producao`)
2. Lider aprova justificativa
3. CAB revisa (se acesso N3/N4)
4. Infra configura acesso
5. Auditoria: sessao gravada

---

## Niveis de Acesso

!!! abstract "Matriz de Acesso"
    | Nivel | Permissao | Aprovacao | Validade |
    |-------|-----------|-----------|----------|
    | N3 | Read-only | CAB + Lider | 6 meses |
    | N4 | Write | CAB + Diretor | 3 meses |

---

## Regras

!!! warning "Obrigatoriedades"
    - Sempre usar jump host
    - Sessao maxima: 4 horas
    - Todos os comandos logados
    - Revogar apos o termino do acesso
