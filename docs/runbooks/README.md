---
title: Runbooks
description: Runbooks de resposta a incidentes, manutencoes e backups
---

# :material-ambulance: Runbooks

<div class="stat-grid" markdown>

<div class="stat-card" markdown>

<div class="stat-icon">:material-alert-circle:</div>
<div class="stat-number">6</div>
<div class="stat-label">Incidentes</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-tools:</div>
<div class="stat-number">4</div>
<div class="stat-label">Manutencoes</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-database-sync:</div>
<div class="stat-number">4</div>
<div class="stat-label">Backups</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-clock-fast:</div>
<div class="stat-number">24h</div>
<div class="stat-label">Disponibilidade</div>

</div>

</div>

---

## :material-alert-circle: Incidentes

| Severidade | Runbook | Tempo Resposta |
|------------|---------|----------------|
| **P1 - Critico** | [Queda de Link](incidentes/queda-link.md) | 15 min |
| **P1 - Critico** | [Servico Down](incidentes/servico-down.md) | 15 min |
| **P2 - Alto** | [Lentidao de Rede](incidentes/lentidao-rede.md) | 30 min |
| **P2 - Alto** | [DDoS](incidentes/ddos.md) | 30 min |
| **P2 - Alto** | [Disco Cheio](incidentes/disco-cheio.md) | 30 min |
| **P3 - Medio** | [SSL Expirado](incidentes/ssl-expirado.md) | 2 horas |

---

## :material-tools: Manutencoes

| Runbook | Frequencia |
|---------|------------|
| [Manutencao de Servidores](manutencoes/manutencao-servidores.md) | Mensal |
| [Patch Management](manutencoes/patch-management.md) | Mensal |
| [Renovacao SSL](manutencoes/renovacao-ssl.md) | Anual |
| [Limpeza de Disco](manutencoes/limpeza-disco.md) | Sob demanda |

---

## :material-database-sync: Backups

| Runbook | Frequencia |
|---------|------------|
| [Backup de Banco](backups/backup-banco.md) | Diario |
| [Backup de Arquivos](backups/backup-arquivos.md) | Diario |
| [Verificacao de Backup](backups/verificacao.md) | Semanal |
| [Restauracao](backups/restauracao.md) | Sob demanda |

---

## :material-phone: Contatos de Emergencia

<div class="contact-grid" markdown>

<div class="contact-item" markdown>

<span class="cicon">:material-phone:</span>
<span class="ctext"><strong>NOC 24h</strong>`(11) 3000-1000`</span>

</div>

<div class="contact-item" markdown>

<span class="cicon">:material-phone:</span>
<span class="ctext"><strong>Eng. Senior</strong>`(11) 9999-8888`</span>

</div>

<div class="contact-item" markdown>

<span class="cicon">:material-phone:</span>
<span class="ctext"><strong>Gerente Infra</strong>`(11) 9999-7777`</span>

</div>

</div>
