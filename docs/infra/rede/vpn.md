---
title: VPN e Acesso Remoto
description: Configuração e acesso remoto via VPN
---

# VPN e Acesso Remoto

## Visão Geral

Guia de acesso remoto via VPN para colaboradores externos e home office.

---

## Tipos de VPN

| Tipo | Uso | Servidor | Cliente |
|------|-----|----------|---------|
| Site-to-Site | Filiais | Fortinet | MikroTik |
| SSL VPN | Home Office | Fortinet | FortiClient |
| IPSec | Parceiros | MikroTik | nativo |

---

## Acesso SSL VPN (Home Office)

### Pré-requisitos

- FortiClient instalado
- Credenciais corporativas
- Token 2FA (Google Authenticator)

### Passo a Passo

1. **Baixe o FortiClient**
    - Windows: [Download](https://www.fortinet.com/products/endpoint-security/forticlient)
    - Mac/Linux: [Download](https://www.fortinet.com/products/endpoint-security/forticlient)

2. **Configure o perfil**
    - Gateway: `vpn.empresa.com.br`
    - Porta: `10443`
    - SSL VPN: `Remote Access`

3. **Conecte**
    - Abra o FortiClient
    - Digite usuário e senha
    - Digite código 2FA
    - Clique em "Connect"

### IP Range VPN

| Rede VPN | CIDR | Uso |
|----------|------|-----|
| VPN Users | `10.10.100.0/24` | Usuários remotos |

---

## Acesso Site-to-Site (Filiais)

| Filial | Rede | Tunnel | Status |
|--------|------|--------|--------|
| Filial SP | `192.168.1.0/24` | IPSec | :material-check-circle: Ativo |
| Filial RJ | `192.168.2.0/24` | IPSec | :material-check-circle: Ativo |

---

## Troubleshooting VPN

| Problema | Causa | Solução |
|----------|-------|---------|
| Não conecta | Credenciais erradas | Verificar usuário/senha |
| Conecta mas não acessa | Rota ausente | Verificar static routes |
| Lentidão | ISP doméstico | Testar banda |
| Desconecta intermitente | Timeout | Ajustar keepalive |

---

## Ver Também

- [Topologia de Rede](topologia.md)
- [Equipamentos de Rede](equipamentos.md)
- [Política de Segurança](../../politicas/seguranca.md)
