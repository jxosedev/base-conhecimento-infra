---
title: Manutencao de Servidores
description: Runbook para manutencao preventiva de servidores
---

# Manutencao de Servidores

## Frequencia

Mensal - Domingo 02h-06h

---

## Checklist

- [ ] Comunicar aos stakeholders
- [ ] Verificar backups
- [ ] Atualizar pacotes
- [ ] Aplicar patches de seguranca
- [ ] Verificar espaco em disco
- [ ] Reiniciar servicos criticos
- [ ] Testar aplicacao
- [ ] Documentar alteracoes

---

## Comandos Utilizados

```bash
# Atualizar pacotes
apt-get update && apt-get upgrade -y

# Limpar pacotes nao utilizados
apt-get autoremove -y

# Verificar servicos
systemctl list-units --type=service --state=running

# Verificar uptime
uptime
```

---

## Ver Tambem

- [Patch Management](patch-management.md)
- [Limpeza de Disco](limpeza-disco.md)
