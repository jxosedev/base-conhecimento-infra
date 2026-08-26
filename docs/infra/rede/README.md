---
title: Rede
description: Documentacao e troubleshooting de rede
---

# :material-network: Rede

!!! info "Documentacao de Rede"
    Guia de troubleshooting, topologia e equipamentos de rede.

---

## :material-map-marker-path: Topologia

A rede da empresa e dividida em segmentos:

| Rede | CIDR | VLAN | Uso |
|------|------|------|-----|
| Producao | `10.0.0.0/24` | 100 | Servidores |
| Desenvolvimento | `10.0.1.0/24` | 200 | Dev/QA |
| DMZ | `10.0.2.0/24` | 50 | Servidores externos |
| Gerenciamento | `10.0.3.0/24` | 99 | OOB/IPMI |

---

## :material-switch-network: Equipamentos Principais

| Equipamento | Modelo | IP |
|-------------|--------|-----|
| Firewall | Fortinet FortiGate 60F | 10.0.2.1 |
| Core Switch | Cisco Catalyst 9300-48T | 10.0.3.10 |
| Roteador | MikroTik CCR1036-12G-4S | 10.0.3.1 |

---

## :material-file-document: Conteudo

- [Topologia Completa](topologia.md) - Diagrama e segmentos
- [Equipamentos](equipamentos.md) - Lista detalhada de todos os equipamentos
- [VPN e Acesso Remoto](vpn.md) - Configuracao de VPN

---

## :material-wrench: Troubleshooting

| Problema | Runbook |
|----------|---------|
| Queda total de link | [Queda de Link](troubleshooting-queda-link.md) |
| Lentidao na rede | [Lentidao de Rede](troubleshooting-lentidao.md) |

---

## :material-phone: Contatos da Equipe de Redes

<div class="contact-grid" markdown>

<div class="contact-card" markdown>

:material-email:{ .icon }

**Eng. de Redes**<br>`rede@empresa.com`

</div>

<div class="contact-card" markdown>

:material-phone:{ .icon }

**NOC 24h**<br>`(11) 3000-1000`

</div>

<div class="contact-card" markdown>

:material-phone:{ .icon }

**ISP Suporte**<br>`(11) 9999-9999`

</div>

</div>
