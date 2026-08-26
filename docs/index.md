---
title: Inicio
description: Base de Conhecimento de Infraestrutura e Suporte TI
---

# :material-server-network: Base de Conhecimento

!!! abstract "Infraestrutura & Suporte TI"
    Documentacao tecnica completa para o time de infraestrutura.
    :material-update: Ultima atualizacao: Agosto 2026

---

## :material-view-dashboard: Resumo

| :material-server: Servidores | :material-network: Rede | :material-ambulance: Runbooks | :material-shield-check: Politicas |
|:---:|:---:|:---:|:---:|
| **7** ativos | **5** documentados | **14** disponiveis | **3** definidas |

---

## :material-lightning-bolt: Acesso Rapido

| Pagina | Descricao |
|--------|-----------|
| [:material-server: Servidores](infra/servidores/README.md) | Documentacao tecnica completa dos servidores |
| [:material-network: Topologia de Rede](infra/rede/topologia.md) | Mapa e segmentos de rede |
| [:material-switch-network: Equipamentos](infra/rede/equipamentos.md) | Firewalls, switches e access points |
| [:material-alert-circle: Runbooks de Incidentes](runbooks/incidentes/README.md) | Procedimentos de resposta a incidentes |
| [:material-account-plus: Onboarding](pop/onboarding.md) | Novos funcionarios |
| [:material-cloud-download: Politica de Backup](politicas/backup.md) | Regras de backup |
| [:material-vpn: VPN e Acesso Remoto](infra/rede/vpn.md) | Configuracao de VPN |
| [:material-phone-alert: Escalonamento](politicas/escalonamento.md) | Canais de emergencia |

---

## :material-folder-open: Secoes

### :material-book-open-variant: Guia de Uso

Como navegar e contribuir com a documentacao.

- :material-play: [Primeiros Passos](guia/primeiros-passos.md)
- :material-pencil: [Como Contribuir](guia/como-contribuir.md)
- :material-file-document: [Padrao de Documentacao](guia/padrao-documentacao.md)

---

### :material-server: Infraestrutura

Documentacao tecnica de servidores, rede e cloud.

- :material-desktop-classic: [Servidores](infra/servidores/README.md) - 7 servidores documentados
- :material-network: [Rede](infra/rede/README.md) - Topologia, equipamentos, VPN
- :material-harddisk: [Armazenamento](infra/armazenamento/README.md) - Storage e backups
- :material-cloud: [Cloud](infra/cloud/README.md) - Servicos em nuvem

---

### :material-ambulance: Runbooks

Procedimentos de resposta a incidentes e manutencoes.

- :material-alert-circle: [Incidentes](runbooks/incidentes/README.md) - Queda de link, DDoS, servico down
- :material-tools: [Manutencoes](runbooks/manutencoes/README.md) - Patches, SSL, limpeza
- :material-database-sync: [Backups](runbooks/backups/README.md) - Backup e restauracao

---

### :material-clipboard-text: Procedimentos (POP)

Fluxos operacionais padrao.

- :material-account-plus: [Onboarding](pop/onboarding.md) - Novos funcionarios
- :material-account-minus: [Offboarding](pop/offboarding.md) - Desligamentos
- :material-key: [Acesso a Producao](pop/acesso-producao.md) - Liberacao de acesso

---

### :material-shield-check: Politicas

Regras e diretrizes da infraestrutura.

- :material-security: [Seguranca](politicas/seguranca.md)
- :material-cloud-download: [Backup](politicas/backup.md)
- :material-phone-alert: [Escalonamento](politicas/escalonamento.md)

---

## :material-wrench: Troubleshooting

| Problema | Runbook |
|----------|---------|
| :material-link-off: Queda total de link | [Queda de Link](infra/rede/troubleshooting-queda-link.md) |
| :material-speedometer: Lentidao na rede | [Lentidao de Rede](infra/rede/troubleshooting-lentidao.md) |

---

## :material-phone: Contatos

| Canal | Contato |
|-------|---------|
| :material-account-group: **Infraestrutura** | `#infra-geral` no Slack |
| :material-network: **Rede** | `#infra-rede` no Slack |
| :material-shield-lock: **Seguranca** | `#seg-info` no Slack |
| :material-phone-alert: **Emergencia 24h** | `(11) 3000-9999` |

---

!!! warning "Mantenha atualizado"
    Encontrou informacao desatualizada? Abra um PR ou avise no canal `#infra-docs`.
