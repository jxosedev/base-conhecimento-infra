---
title: Rede
description: Documentacao e troubleshooting de rede
---

# :material-network: Rede

!!! info "Documentacao de Rede"
    Guia de troubleshooting, topologia e equipamentos de rede.

---

## Resumo

| Firewall | Core Switch | Roteador | Access Points |
|:---:|:---:|:---:|:---:|
| **1** | **1** | **1** | **2** |

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

| Pagina | Descricao |
|--------|-----------|
| [:material-map-marker-path: Topologia Completa](topologia.md) | Diagrama e segmentos de rede |
| [:material-switch-network: Equipamentos](equipamentos.md) | Firewall, switches, roteadores |
| [:material-vpn: VPN e Acesso Remoto](vpn.md) | Configuracao de VPN |
| [:material-link-off: Queda de Link](troubleshooting-queda-link.md) | Troubleshooting de link |
| [:material-speedometer: Lentidao de Rede](troubleshooting-lentidao.md) | Diagnosticos de lentidao |

---

## :material-phone: Contatos da Equipe de Redes

| Funcao | Contato |
|--------|---------|
| :material-email: **Eng. de Redes** | `rede@empresa.com` |
| :material-phone: **NOC 24h** | `(11) 3000-1000` |
| :material-phone: **ISP Suporte** | `(11) 9999-9999` |
