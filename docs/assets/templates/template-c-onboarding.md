---
title: "POP — Onboarding de Funcionário (TI)"
description: "Procedimento Operacional Padrão para admissão de novos colaboradores no time de TI."
tags: [pop, onboarding, rh, ti, admissao]
---

# POP — Onboarding de Funcionário (TI)

!!! info "Resumo do Procedimento"
    | Campo | Valor |
    |-------|-------|
    | **Código** | POP-TI-003 |
    | **Versão** | 2.1 |
    | **Responsável** | Coordenação de TI |
    | **SLA** | Conta criada em até **4h úteis** após aprovação do RH |
    | **Ferramentas** | Active Directory, Google Workspace, Jira, Slack, Vault |

---

## Escopo

!!! tip "Este POP se aplica a:"
    - **Novos funcionários** do time de TI (dev, infra, suporte, segurança)
    - **Estagiários** do time de TI
    - **Funcionários transferidos** para o time de TI
    - **Terceiros/consultores** com acesso temporário (usar procedure específica)

!!! warning "Este POP NÃO se aplica a:"
    - Funcionários de outros departamentos (ver POP-TI-001)
    - Acesso a sistemas específicos que exigem aprovação adicional (ex: AWS, GCP)
    - Acesso a ambientes de Produção (requer CAB)

---

## Pré-requisitos

!!! abstract "Antes de iniciar, confirme:"
    - [ ] E-mail de aprovação do RH recebido com: nome completo, CPF, cargo, data de admissão, matrícula
    - [ ] Acesso ao painel de administração (AD/Google Admin)
    - [ ] Senha temporária gerada (Vault ou ferramenta interna)
    - [ ] Equipamento (notebook/monitor) disponível e formatado

---

## Fluxo do Onboarding

### Fase 1 — Contas e Acesso Básico

!!! danger "PASSO 1: Criar conta no Active Directory"
    **Prazo:** Até 4h após recebimento do chamado do RH

    1. Acessar painel AD: `https://ad.empresa.com/admin`
    2. Criar usuário com padrão: `primeiro.ultimo`
    3. Definir grupo: `TI-Staff`
    4. Senha temporária ( Vault: `vault read infra/ad/tempsenha` )
    4. Forçar troca de senha no primeiro login
    5. Verificar que o usuário consegue autenticar

    !!! example "Dados para cadastro"
        ```
        Nome: [NOME COMPLETO]
        Usuário: [primeiro.ultimo]
        E-mail: [primeiro.ultimo]@empresa.com
        Grupo: TI-Staff
        OU: OU=TI,OU=Funcionarios,DC=empresa,DC=com
        ```

!!! danger "PASSO 2: Criar e-mail corporativo (Google Workspace)"
    **Prazo:** Até 2h após criação do AD

    1. Acessar Google Admin: `https://admin.google.com`
    2. Criar usuário: `primeiro.ultimo@empresa.com`
    3. Adicionar ao grupo: `ti-all@empresa.com`
    4. Licença: Google Workspace Business Standard
    5. Verificar recebimento de e-mail de boas-vindas

!!! warning "PASSO 3: Configurar VPN"
    1. Gerar certificado VPN (WireGuard/OpenVPN)
    2. Adicionar peer no `wg0.conf` do servidor
    3. Entregar arquivo de configuração ao funcionário
    4. Testar conectividade: `ping 10.10.1.1`

---

### Fase 2 — Ferramentas do Time

!!! note "PASSO 4: Acesso ao Jira"
    1. Adicionar ao projeto: `TI`
    2. Permissão: `Project Member` (criar issues, comentar)
    3. Adicionar ao board: `TI Board - Sprint`
    4. Enviar convite por e-mail

!!! note "PASSO 5: Acesso ao Slack"
    1. Adicionar workspace: `empresa.slack.com`
    2. Canais obrigatórios:
        - `#ti-geral`
        - `#ti-alertas`
        - `#incidents`
        - `#ti-onboarding`
    3. Perfil: adicionar foto e cargo

!!! note "PASSO 6: Acesso ao Confluence/Documentação"
    1. Adicionar ao espaço: `TI - Base de Conhecimento`
    2. Permissão: `Edit`
    3. Apresentar estrutura do MkDocs

---

### Fase 3 — Acesso a Servidores (Conforme cargo)

!!! abstract "PASSO 7: Acesso a servidores"
    **Aplicável apenas para:** DevOps, Infraestrutura, SRE

    | Nível | Acesso | Aprovação |
    |-------|--------|-----------|
    | **N1** | Homologação (read/write) | Líder de equipe |
    | **N2** | Staging (read/write) | Líder de equipe |
    | **N3** | Produção (read only) | CAB + Líder |
    | **N4** | Produção (write) | CAB + Diretor de TI |

    !!! danger "Regras para acesso a Produção"
        - Sempre usar jump host
        - Jamais usar root diretamente
        - Cada comando deve ser registrado
        - Sessão máxima: 4 horas
        - Auditoria: todas as sessões gravadas

!!! example "Comandos para dar acesso (Linux)"
    ```bash
    # Adicionar ao grupo SSH do servidor
    sudo usermod -aG ssh-users primeiro.ultimo

    # Copiar chave pública
    ssh-copy-id -i ~/.ssh/id_rsa.pub primeiro.ultimo@gateway.intranet

    # Testar acesso
    ssh -o ConnectTimeout=5 primeiro.ultimo@gateway.intranet
    ```

---

### Fase 4 — Segurança e Compliance

!!! danger "PASSO 8: Política de Senha e Segurança"
    1. Orientar sobre política de senhas:
        - Mínimo 12 caracteres
        - Mistura de maiúsculas, minúsculas, números e símbolos
        - Não reutilizar senhas anteriores
        - Usar gerenciador de senhas (1Password/Bitwarden)
    2. Habilitar MFA/2FA em todas as contas
    3. Assinar termo de responsabilidade de TI

!!! warning "PASSO 9: Política de Backup Local"
    1. Configurar backup automático do notebook (Backblaze/Time Machine)
    2. Orientar sobre backup de dados sensíveis
    3. Explicar política de retenção de dados

---

### Fase 5 — Integração e Mentoria

!!! tip "PASSO 10: Onboarding Cultural"
    1. Apresentar ao time (canal `#ti-onboarding`)
    2. Agendar 1:1 com líder de equipe
    3. Designar um buddy/mentor para as primeiras 2 semanas
    4. Agendar treinamentos:
        - Segurança da informação (1h)
        - Uso de ferramentas internas (2h)
        - Processos de deploy e CI/CD (2h)
        - Fluxo de chamados e incidentes (1h)

!!! note "Checklist de Mentoria"
    - [ ] Dia 1: Apresentação com time e líder
    - [ ] Dia 1: Tour pelas ferramentas (Slack, Jira, Confluence)
    - [ ] Dia 2: Acesso a todos os sistemas confirmados
    - [ ] Dia 3: Primeiro commit / primeira tarefa
    - [ ] Semana 1: Review de acessos com líder
    - [ ] Semana 2: Feedback do buddy
    - [ ] Mês 1: Avaliação de onboarding com RH

---

## Checklist Final

!!! abstract "Ao finalizar o onboarding, confirme:"
    - [ ] Conta AD criada e funcionando
    - [ ] E-mail corporativo ativo
    - [ ] VPN configurada e testada
    - [ ] Slack configurado com canais corretos
    - [ ] Jira com acesso ao projeto
    - [ ] Acesso a servidores conforme cargo
    - [ ] MFA habilitado em todas as contas
    - [ ] Termo de responsabilidade assinado
    - [ ] Buddy/mentor designado
    - [ ] Treinamentos agendados
    - [ ] Equipamento entregue e configurado
    - [ ] Chamado de onboarding encerrado

---

## Prazos e SLAs

!!! warning "Tempos máximos permitidos"
    | Etapa | Prazo |
    |-------|-------|
    | Conta AD + E-mail | 4h úteis |
    | VPN | 8h úteis |
    | Ferramentas (Jira/Slack) | 24h úteis |
    | Acesso a servidores | 48h úteis |
    | Treinamentos | 5 dias úteis |

---

## Troubleshooting do Onboarding

!!! tip "Problemas comuns"
    **Usuário não consegue logar no AD:**
    - Verificar se a conta foi criada no OU correto
    - Confirmar que a senha temporária está correta
    - Verificar se o usuário foi adicionado ao grupo correto

    **E-mail não está recebendo:**
    - Verificar se o domínio MX está apontando para Google
    - Confirmar que a licença foi atribuída
    - Testar com outro remetente

    **VPN não conecta:**
    - Verificar se o certificado não expirou
    - Confirmar IP do servidor VPN
    - Testar com outro dispositivo

---

## Contatos

| Finalidade | Contato |
|------------|---------|
| **Dúvidas sobre este POP** | `ti-coordenacao@empresa.com` |
| **Suporte AD** | `suporte-ad@empresa.com` |
| **Suporte Google** | `suporte-google@empresa.com` |
| **RH (chamados)** | `rh-admissao@empresa.com` |
| **Emergência TI** | `(11) 3000-9999` |

---

!!! tip "POP atualizado em 2026-08-25"
    Versão: 2.1 | Autor: Coordenação de TI
