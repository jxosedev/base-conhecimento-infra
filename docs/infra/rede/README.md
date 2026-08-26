---
title: Rede
description: Documentacao e troubleshooting de rede
---

# :material-network: Rede

<div class="stat-grid" markdown>

<div class="stat-card" markdown>

<div class="stat-icon">:material-fire:</div>
<div class="stat-number">1</div>
<div class="stat-label">Firewall</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-switch-network:</div>
<div class="stat-number">1</div>
<div class="stat-label">Core Switch</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-router-network:</div>
<div class="stat-number">1</div>
<div class="stat-label">Roteador</div>

</div>

<div class="stat-card" markdown>

<div class="stat-icon">:material-access-point-network:</div>
<div class="stat-number">2</div>
<div class="stat-label">Access Points</div>

</div>

</div>

---

## :material-map-marker-path: Segmentos de Rede

| Rede | CIDR | VLAN | Uso |
|------|------|------|-----|
| Producao | `10.0.0.0/24` | 100 | Servidores |
| Desenvolvimento | `10.0.1.0/24` | 200 | Dev/QA |
| DMZ | `10.0.2.0/24` | 50 | Servidores externos |
| Gerenciamento | `10.0.3.0/24` | 99 | OOB/IPMI |

---

## :material-file-document: Conteudo

<div class="quick-grid" markdown>

<a href="topologia.md" class="quick-card" markdown>

<span class="qicon">:material-map-marker-path:</span>
<span class="qtext"><span class="qtitle">Topologia Completa</span><span class="qdesc">Diagrama e segmentos de rede</span></span>

</a>

<a href="equipamentos.md" class="quick-card" markdown>

<span class="qicon">:material-switch-network:</span>
<span class="qtext"><span class="qtitle">Equipamentos</span><span class="qdesc">Firewall, switches, roteadores</span></span>

</a>

<a href="vpn.md" class="quick-card" markdown>

<span class="qicon">:material-vpn:</span>
<span class="qtext"><span class="qtitle">VPN e Acesso Remoto</span><span class="qdesc">Configuracao de VPN</span></span>

</a>

<a href="troubleshooting-queda-link.md" class="quick-card" markdown>

<span class="qicon">:material-link-off:</span>
<span class="qtext"><span class="qtitle">Queda de Link</span><span class="qdesc">Troubleshooting de link</span></span>

</a>

<a href="troubleshooting-lentidao.md" class="quick-card" markdown>

<span class="qicon">:material-speedometer:</span>
<span class="qtext"><span class="qtitle">Lentidao de Rede</span><span class="qdesc">Diagnosticos de lentidao</span></span>

</a>

</div>

---

## :material-phone: Contatos da Equipe de Redes

<div class="contact-grid" markdown>

<div class="contact-item" markdown>

<span class="cicon">:material-email:</span>
<span class="ctext"><strong>Eng. de Redes</strong>`rede@empresa.com`</span>

</div>

<div class="contact-item" markdown>

<span class="cicon">:material-phone:</span>
<span class="ctext"><strong>NOC 24h</strong>`(11) 3000-1000`</span>

</div>

<div class="contact-item" markdown>

<span class="cicon">:material-phone:</span>
<span class="ctext"><strong>ISP Suporte</strong>`(11) 9999-9999`</span>

</div>

</div>
