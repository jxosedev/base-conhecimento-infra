---
title: Equipamentos de Rede
description: Lista e especificações dos equipamentos de rede
---

# Equipamentos de Rede

## Visão Geral

Inventário completo dos equipamentos de rede da infraestrutura.

---

## Firewalls

| Modelo | IP | Serial | Localização | Status |
|--------|-----|--------|-------------|--------|
| Fortinet FortiGate 60F | `10.0.2.1` | FG-001 | Datacenter | :material-check-circle: Ativo |

**Configurações:**
- Firmware: 7.2.6
- Licença: Enterprise Until 2027
- HA: Não configurado

---

## Switches

| Modelo | IP | Portas | Uplink | Localização | Status |
|--------|-----|--------|--------|-------------|--------|
| Cisco Catalyst 9300-48T | `10.0.3.10` | 48x 1G | 2x 10G SFP+ | Datacenter | :material-check-circle: Ativo |

**Configurações:**
- IOS: 17.9.4a
- VLANs: 50, 99, 100, 200
- Spanning-tree: RSTP

---

## Roteadores

| Modelo | IP | WAN | LAN | Status |
|--------|-----|-----|-----|--------|
| MikroTik CCR1036-12G-4S | `10.0.3.1` | 500Mbps | 10G | :material-check-circle: Ativo |

**Configurações:**
- RouterOS: 7.12
- Queue: Simple queues por IP
- Firewall: Mangle + Queue tree

---

## Access Points

| Modelo | IP | SSID | Banda | Status |
|--------|-----|------|-------|--------|
| Ubiquiti UniFi AP-AC-Pro | `10.0.2.10` | Corp-5G | 5GHz | :material-check-circle: Ativo |
| Ubiquiti UniFi AP-AC-Pro | `10.0.2.11` | Corp-2.4G | 2.4GHz | :material-check-circle: Ativo |

---

## Manutenção Preventiva

| Equipamento | Frequência | Última Revisão | Próxima |
|-------------|------------|----------------|---------|
| Firewall | Mensal | 01/08/2026 | 01/09/2026 |
| Switches | Trimestral | 15/07/2026 | 15/10/2026 |
| Roteadores | Mensal | 01/08/2026 | 01/09/2026 |

---

## Ver Também

- [Topologia de Rede](topologia.md)
- [Troubleshooting de Queda de Link](troubleshooting-queda-link.md)
