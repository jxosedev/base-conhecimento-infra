---
title: DDoS
description: Runbook para mitigacao de ataques DDoS
---

# DDoS

## Sintomas

- Alto trafego incomum
- Servicos lentos ou indisponiveis
- CPU/memoria no limite

---

## Diagnostico Rapido

### 1. Verificar trafego

```bash
iftop -i eth0
nethogs eth0
```

### 2. Verificar conexoes

```bash
/ss tool traffic-print
/ip firewall connection print
```

---

## Acao Imediata

1. **Ativar blackhole** no ISP/Firewall
2. **Bloquear IPs** suspeitos
3. **Ativar rate limit** no firewall
4. **Escalar** para NOC e provedor

---

## Comandos de Emergencia (MikroTik)

```bash
# Blackhole
/ip route add dst-address=<ip_atacante>/32 blackhole

# Bloquear IP
/ip firewall address-list add list=ddos address=<ip>
/ip firewall filter add chain=forward src-address-list=ddos action=drop
```

---

## Ver Tambem

- [Queda de Link](queda-link.md)
- [Topologia de Rede](../../infra/rede/topologia.md)
