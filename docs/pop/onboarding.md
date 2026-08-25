---
title: POP — Onboarding de Funcionario (TI)
description: Procedimento Operacional Padrao para admissao de novos colaboradores no time de TI.
tags: [pop, onboarding, rh, ti, admissao]
---

# POP — Onboarding de Funcionario (TI)

!!! info "Resumo do Procedimento"
    | Campo | Valor |
    |-------|-------|
    | **Codigo** | POP-TI-003 |
    | **Versao** | 2.1 |
    | **Responsavel** | Coordenacao de TI |
    | **SLA** | Conta criada em ate **4h uteis** apos aprovacao do RH |

---

## Escopo

!!! tip "Este POP se aplica a:"
    - Novos funcionarios do time de TI
    - Estagiarios do time de TI
    - Funcionarios transferidos para o time de TI

---

## Fluxo do Onboarding

### Fase 1 — Contas e Acesso Basico

!!! danger "PASSO 1: Criar conta no Active Directory"
    **Prazo:** Ate 4h apos recebimento do chamado do RH

    1. Acessar painel AD: `https://ad.empresa.com/admin`
    2. Criar usuario com padrao: `primeiro.ultimo`
    3. Definir grupo: `TI-Staff`
    4. Senha temporaria via Vault
    5. Forcar troca de senha no primeiro login

!!! danger "PASSO 2: Criar e-mail corporativo"
    **Prazo:** Ate 2h apos criacao do AD

    1. Google Admin: `https://admin.google.com`
    2. Criar usuario: `primeiro.ultimo@empresa.com`
    3. Grupo: `ti-all@empresa.com`
    4. Licenca: Google Workspace Business Standard

!!! warning "PASSO 3: Configurar VPN"
    1. Gerar certificado VPN (WireGuard)
    2. Adicionar peer no servidor
    3. Entregar arquivo de configuracao
    4. Testar conectividade

---

### Fase 2 — Ferramentas do Time

!!! note "PASSO 4: Acesso ao Jira"
    1. Projeto: `TI`
    2. Permissao: `Project Member`
    3. Board: `TI Board - Sprint`

!!! note "PASSO 5: Acesso ao Slack"
    Canais obrigatorios: `#ti-geral`, `#ti-alertas`, `#incidents`, `#ti-onboarding`

---

### Fase 3 — Acesso a Servidores

!!! abstract "PASSO 7: Acesso a servidores"
    | Nivel | Acesso | Aprovacao |
    |-------|--------|-----------|
    | N1 | Homologacao (read/write) | Lider |
    | N2 | Staging (read/write) | Lider |
    | N3 | Producao (read only) | CAB + Lider |
    | N4 | Producao (write) | CAB + Diretor |

---

### Fase 4 — Seguranca

!!! danger "PASSO 8: Politica de Senha"
    - Minimo 12 caracteres
    - MFA obrigatorio em todas as contas
    - Assinar termo de responsabilidade

---

## Checklist Final

!!! abstract "Ao finalizar:"
    - [ ] Conta AD criada
    - [ ] E-mail ativo
    - [ ] VPN configurada
    - [ ] Slack com canais corretos
    - [ ] Jira acessivel
    - [ ] Acesso a servidores
    - [ ] MFA habilitado
    - [ ] Termo assinado
    - [ ] Buddy designado
    - [ ] Treinamentos agendados

---

!!! tip "Atualizado em 2026-08-25 | Versao 2.1"
