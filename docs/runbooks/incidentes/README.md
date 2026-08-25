---
title: Incidentes
description: Runbooks de resposta a incidentes
---

# Runbooks de Incidentes

!!! danger "Em caso de incidente"
    Siga o runbook correspondente e abra um chamado imediatamente.

---

## Runbooks Disponiveis

| Incidente | Severidade | Runbook |
|-----------|------------|---------|
| Queda de link | P1 | [Queda de Link](queda-link.md) |
| Lentidao de rede | P2 | [Lentidao](lentidao-rede.md) |
| Servico indisponivel | P1 | [Servico Down](servico-down.md) |
| Ataque DDoS | P1 | [DDoS](ddos.md) |
| Falta de disco | P2 | [Disco Cheio](disco-cheio.md) |
| Certificado SSL expirado | P2 | [SSL](ssl-expirado.md) |

---

## Fluxo Geral de Incidentes

1. **Detectar**: Alerta automatizado ou relato de usuario
2. **Classificar**: Definir severidade (P1-P4)
3. **Notificar**: Canal `#incidents` no Slack
4. **Diagnosticar**: Seguir runbook correspondente
5. **Resolver**: Executar acoes corretivas
6. **Documentar**: Preencher pos-incidente
