---
title: Renovacao SSL
description: Runbook para renovacao de certificados SSL
---

# Renovacao SSL

## Frequencia

Anual (ou automatica via Let's Encrypt)

---

## Procedimento

### Let's Encrypt (Automatico)

```bash
# Verificar certificados
certbot certificates

# Renovar
certbot renew

# Verificar renewal timer
systemctl status certbot.timer
```

### Certificado Comercial

1. Verificar data de expiracao
2. Gerar nova CSR
3. Solicitar renovacao ao fornecedor
4. Validar dominio
5. Instalar novo certificado
6. Reiniciar servicos

---

## Ver Tambem

- [SSL Expirado](../incidentes/ssl-expirado.md)
- [Manutencao de Servidores](manutencao-servidores.md)
