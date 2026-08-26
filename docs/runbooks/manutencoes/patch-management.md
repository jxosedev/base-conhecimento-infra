---
title: Patch Management
description: Runbook para gerenciamento de patches
---

# Patch Management

## Frequencia

Mensal

---

## Fluxo

1. **Identificar patches** disponiveis
2. **Classificar** por severidade
3. **Testar** em ambiente de dev
4. **Agendar** manutencao
5. **Aplicar** em producao
6. **Verificar** pos-atualizacao

---

## Classificacao

| Severidade | Prazo | Exemplo |
|------------|-------|---------|
| Critica | 24h | CVE remoto |
| Alta | 7 dias | Privilege escalation |
| Media | 30 dias | Correcao de bug |
| Baixa | proximo ciclo | Melhoria |

---

## Ver Tambem

- [Manutencao de Servidores](manutencao-servidores.md)
- [Seguranca](../../politicas/seguranca.md)
