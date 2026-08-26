---
title: Runbooks
description: Runbooks de resposta a incidentes, manutencoes e backups
---

# :material-ambulance: Runbooks

!!! info "Runbooks Disponiveis"
    Procedimentos padronizados para resposta a incidentes, manutencoes e backups.

---

## Resumo

| Incidentes | Manutencoes | Backups | Disponibilidade |
|:---:|:---:|:---:|:---:|
| **6** | **4** | **4** | **24h** |

---

## :material-alert-circle: Incidentes

| Severidade | Runbook | Tempo Resposta |
|------------|---------|----------------|
| **P1 - Critico** | [:material-link-off: Queda de Link](incidentes/queda-link.md) | 15 min |
| **P1 - Critico** | [:material-server-off: Servico Down](incidentes/servico-down.md) | 15 min |
| **P2 - Alto** | [:material-speedometer: Lentidao de Rede](incidentes/lentidao-rede.md) | 30 min |
| **P2 - Alto** | [:material-shield-half-full: DDoS](incidentes/ddos.md) | 30 min |
| **P2 - Alto** | [:material-harddisk: Disco Cheio](incidentes/disco-cheio.md) | 30 min |
| **P3 - Medio** | [:material-lock-open: SSL Expirado](incidentes/ssl-expirado.md) | 2 horas |

---

## :material-tools: Manutencoes

| Runbook | Frequencia |
|---------|------------|
| [:material-server: Manutencao de Servidores](manutencoes/manutencao-servidores.md) | Mensal |
| [:material-update: Patch Management](manutencoes/patch-management.md) | Mensal |
| [:material-certificate: Renovacao SSL](manutencoes/renovacao-ssl.md) | Anual |
| [:material-broom: Limpeza de Disco](manutencoes/limpeza-disco.md) | Sob demanda |

---

## :material-database-sync: Backups

| Runbook | Frequencia |
|---------|------------|
| [:material-database: Backup de Banco](backups/backup-banco.md) | Diario |
| [:material-folder-zip: Backup de Arquivos](backups/backup-arquivos.md) | Diario |
| [:material-check-circle: Verificacao](backups/verificacao.md) | Semanal |
| [:material-restore: Restauracao](backups/restauracao.md) | Sob demanda |

---

## :material-phone: Contatos de Emergencia

| Funcao | Contato | Disponibilidade |
|--------|---------|-----------------|
| :material-phone: **NOC 24h** | `(11) 3000-1000` | 24/7 |
| :material-phone: **Eng. Senior** | `(11) 9999-8888` | 24/7 (P1) |
| :material-phone: **Gerente Infra** | `(11) 9999-7777` | Horario comercial |
