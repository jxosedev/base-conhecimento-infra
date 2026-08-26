---
title: SSL Expirado
description: Runbook para renovacao de certificados SSL
---

# SSL Expirado

## Sintomas

- Navegador mostra erro de certificado
- APIs retornam erro de TLS
- Usuarios nao conseguem acessar sites

---

## Diagnostico Rapido

### 1. Verificar certificado

```bash
echo | openssl s_client -connect dominio.com:443 2>/dev/null | openssl x509 -noout -dates
```

### 2. Verificar Let's Encrypt

```bash
certbot certificates
```

---

## Renovacao

### Let's Encrypt

```bash
certbot renew
systemctl reload nginx
```

### Certificado Manual

1. Gerar CSR
2. Enviar para CA
3. Baixar certificado
4. Instalar no servidor
5. Reiniciar servico

---

## Ver Tambem

- [Manutencao de Servidores](../manutencoes/manutencao-servidores.md)
