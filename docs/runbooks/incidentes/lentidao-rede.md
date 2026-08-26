---
title: Lentidao de Rede
description: Runbook para resolucao de lentidao de rede
---

# Lentidao de Rede

## Sintomas

- Lentidao ao acessar sistemas
- Downloads lentos
- Alto uso de CPU nos switches

---

## Diagnostico Rapido

### 1. Verificar utilizacao de banda

```bash
/interface monitor ethernet1
/tool bandwidth-test 8.8.8.8 duration=30
```

### 2. Verificar erros na interface

```bash
/interface ethernet monitor [find]
```

### 3. Verificar CPU

```bash
/system resource print
```

---

## Causas Comuns

| Causa | Sintoma | Solucao |
|-------|---------|---------|
| Broadcast storm | CPU 100% | Isolar origem, STP |
| Duplex mismatch | Erros CRC | Ajustar velocidade |
| Banda saturada | Downloads lentos | QoS / Rate limit |
| Cabo ruim | Lentidao intermitente | Substituir cabo |

---

## Ver Tambem

- [Queda de Link](queda-link.md)
- [Equipamentos de Rede](../../infra/rede/equipamentos.md)
