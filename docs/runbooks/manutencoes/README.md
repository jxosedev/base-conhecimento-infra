---
title: Manutenções
description: Runbooks de manutenção preventiva e corretiva
---

# Runbooks de Manutenção

## Visão Geral

Procedimentos de manutenção preventiva e corretiva dos sistemas.

---

## Tipos de Manutenção

| Tipo | Frequência | Janela | Aprovação |
|------|------------|--------|-----------|
| Preventiva | Mensal | Domingo 02h-06h | Gerente |
| Corretiva | Sob demanda | Variável | Incidente |
| Emergencial | Sob demanda | Imediato | NOC |

---

## Runbooks Disponíveis

| Runbook | Descrição | Frequência |
|---------|-----------|------------|
| [Manutenção de Servidores](manutencao-servidores.md) | Updates, patches, limpeza | Mensal |
| [Patch Management](patch-management.md) | Instalação de patches segurança | Mensal |
| [Renovação SSL](renovacao-ssl.md) | Renovação de certificados | Anual |
| [Limpeza de Disco](limpeza-disco.md) | Liberação de espaço em disco | Sob demanda |

---

## Checklist Padrão

- [ ] Comunicar aos stakeholders
- [ ] Verificar backups atualizados
- [ ] Preparar rollbacks
- [ ] Monitorar durante manutenção
- [ ] Testar após aplicação
- [ ] Documentar alterações
- [ ] Atualizar CMDB

---

## Ver Também

- [Incidentes](../incidentes/README.md)
- [Backups](../backups/README.md)
