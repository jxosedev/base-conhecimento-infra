---
title: Backups
description: Runbacks de backup e restauração
---

# Runbooks de Backup

## Visão Geral

Procedimentos de backup, verificação e restauração de dados.

---

## Política de Backup

| Dados | Frequência | Retenção | Destino |
|-------|------------|----------|---------|
| Bancos de dados | Diário 02h | 30 dias | S3 |
| Configurações | Semanal | 90 dias | Git |
| Snapshots VM | Semanal | 4 semanas | vSphere |
| Arquivos críticos | Diário | 30 dias | S3 |

---

## Runbooks Disponíveis

| Runbook | Descrição |
|---------|-----------|
| [Backup de Banco](backup-banco.md) | Dump e restauração PostgreSQL |
| [Backup de Arquivos](backup-arquivos.md) | Backup de diretórios críticos |
| [Verificação de Backup](verificacao.md) | Teste de integridade |
| [Restauração](restauracao.md) | Processo de restore |

---

## Verificação Automática

| Verificação | Frequência | Ação |
|-------------|------------|------|
| Integrity check | Diário | Alerta Slack |
| Restore test | Semanal | Relatório |
| Capacity planning | Mensal | Relatório |

---

## Contatos

| Função | Contato |
|--------|---------|
| Responsável Backup | `backup@empresa.com` |
| NOC | `(11) 3000-1000` |

---

## Ver Também

- [Incidentes](../incidentes/README.md)
- [Manutenções](../manutencoes/README.md)
