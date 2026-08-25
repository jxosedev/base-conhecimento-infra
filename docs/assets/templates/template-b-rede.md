---
title: "Guia de Troubleshooting — Problemas de Rede"
description: "Fluxo de diagnóstico e resolução de problemas de rede."
tags: [rede, troubleshooting, runbook, diagnostico]
---

# Guia de Troubleshooting — Problemas de Rede

!!! danger "QUANDO USAR ESTE GUIA"
    Use este runbook quando houver relato de **queda de link**, **lentidão de rede**, **perda de pacotes** ou **instabilidade generalizada**.

---

## Classificação do Problema

!!! warning "Classifique ANTES de iniciar diagnóstico"
    | Severidade | Descrição | SLA de Resposta |
    |------------|-----------|-----------------|
    | **P1 - Crítico** | Link da empresa DOWN, mais de 50% dos usuários afetados | 15 min |
    | **P2 - Alto** | Lentidão generalizada ou perda pacotes > 5% | 30 min |
    | **P3 - Médio** | Problema isolado em setor específico | 2h |
    | **P4 - Baixo** | Instabilidade pontual, sem impacto significativo | 4h |

---

## Passo 1 — Coleta Inicial

!!! note "Verificar relato do usuário"
    1. Qual setor/andar está afetado?
    2. É intermitente ou contínuo?
    3. Aconteceu após alguma mudança (manutenção, novo equipamento)?
    4. Todos da equipe estão com problema ou apenas um usuário?

!!! example "Comandos iniciais de verificação"
    ```bash
    # Testar conectividade básica
    ping -c 10 8.8.8.8
    ping -c 10 gateway.local

    # Verificar perda de pacotes (múltiplos saltos)
    traceroute 8.8.8.8

    # Testar resolução DNS
    nslookup google.com
    dig google.com +short

    # Verificar portas essenciais
    nc -zv 10.10.1.1 80 443 53
    ```

---

## Passo 2 — Verificação no Equipamento de Rede

!!! abstract "Checklist — Switch/Router"
    - [ ] Status das interfaces (up/down/errdisable)
    - [ ] Utilização de CPU e memória
    - [ ] Tabela MAC/ARP
    - [ ] VLANs configuradas corretamente
    - [ ] Spanning Tree (portas bloqueadas?)
    - [ ] Logs do设备 (erros recentes)

!!! example "Comandos Cisco IOS"
    ```bash
    # Status das interfaces
    show ip interface brief
    show interfaces status

    # Verificar erros
    show interfaces counters errors
    show log | include %LINEPROTO

    # Tabela MAC
    show mac address-table

    # Verificar CPU/Memória
    show processes cpu sorted
    show memory statistics

    # VLANs
    show vlan brief
    ```

!!! example "Comandos Mikrotik RouterOS"
    ```bash
    /interface print stats-detail
    /ip arp print
    /ip route print
    /log print where topics~"interface"
    /tool bandwidth-test address=10.10.1.1
    ```

---

## Passo 3 — Diagnóstico por Cenário

### Cenário A: Queda de Link (ISP)

!!! danger "Link externo indisponível"
    **Sinais:**
    - Interface do wan DOWN
    - Todos os serviços externos inacessíveis
    - IP público não responde a ping

    **Procedimento:**
    1. Verificar status da interface WAN: `show ip interface brief`
    2. Verificar se o LED físico do link está aceso
    3. Testar com cabo de rede novo/diferente
    4. Verificar BGP/OSPF adjacency (se aplicável)
    5. Acionar ISP com ticket de emergência
    6. Ativar link 4G/5G como backup (se disponível)

!!! warning "Dados para acionamento do ISP"
    - **Contrato:** `XXXX-YYYY`
    - **Circuit ID:** `CIR-12345`
    - **IP Bloco:** `203.0.113.0/24`
    - **Suporte 24h:** `(11) 9999-9999`
    - **Ticket recente:** `#SUP-12345`

### Cenário B: Lentidão / Perda de Pacotes

!!! warning "Performance degradada"
    **Sinais:**
    - Ping com latência > 100ms ou pacotes perdidos > 5%
    - Downloads muito lentos
    - Aplicações web com timeout

    **Procedimento:**
    1. Executar teste de banda: `iperf3 -c 10.10.1.1 -t 30`
    2. Verificar interface com mais tráfego: `show interfaces utilization`
    3. Checar se há broadcast storm: `show interfaces counters broadcast`
    4. Verificar MTU em toda a path: `ping -s 1472 -M do 10.10.1.1`
    5. Analisar flows/top talkers: `show ip cache flow`
    6. Verificar saturação do link: `show interfaces counters rate`

### Cenário C: Problema Isolado (1 Usuário/Setor)

!!! tip "Caso pontual"
    **Sinais:**
    - Apenas um usuário ou um andar afetado
    - Outros do mesmo setor funcionando

    **Procedimento:**
    1. Verificar porta do switch: `show interface Gi0/X`
    2. Testar com notebook de outro usuário
    3. Verificar VLAN do setor
    4. Testar cabearia: `cable-tester`
    5. Verificar se há IP duplicado (conflito ARP)
    6. Resetar porta do switch se necessário

---

## Passo 4 — Testes de Rede Avançados

!!! example "Scripts de diagnóstico"
    ```bash
    #!/bin/bash
    # diagnose_network.sh - Executar diagnóstico completo

    TARGET=${1:-8.8.8.8}
    INTERFACE=${2:-eth0}

    echo "=== DIAGNÓSTICO DE REDE $(date) ==="

    echo -e "\n--- Conectividade ---"
    ping -c 10 -W 2 $TARGET

    echo -e "\n--- Traceroute ---"
    traceroute -n -w 3 $TARGET

    echo -e "\n--- DNS ---"
    dig google.com +short
    dig @8.8.8.8 google.com +short

    echo -e "\n--- Interface $INTERFACE ---"
    ip -s link show $INTERFACE
    ethtool $INTERFACE | grep -i "speed\|duplex\|link detected"

    echo -e "\n--- Rotas ---"
    ip route show
    ip route get $TARGET

    echo -e "\n--- Conexões ativas ---"
    ss -tunapl | head -20

    echo -e "\n--- Speed test ---"
    speedtest-cli --simple 2>/dev/null || echo "speedtest-cli não instalado"

    echo -e "\n=== FIM DO DIAGNÓSTICO ==="
    ```

---

## Passo 5 — Escalamento

!!! danger "Quando escalar?"
    - Se o problema persistir após 15 minutos de diagnóstico (P1/P2)
    - Se envolver equipamento de rede de Core/Data Center
    - Se houver necessidade de acesso ao ISP ou vendor

!!! note "Contatos de Escalamento"
    | Nível | Responsável | Contato |
    |-------|-------------|---------|
    | **N1** | NOC | `noc@empresa.com` / `(11) 3000-1000` |
    | **N2** | Eng. de Redes | `rede@empresa.com` / `(11) 3000-2000` |
    | **N3** | Infra Sênior | `infra-senior@empresa.com` / `(11) 3000-3000` |
    | **ISP** | Suporte Técnico | `(11) 9999-9999` |

---

## Passo 6 — Registro e Fechamento

!!! abstract "Após resolução, registrar:"
    - [ ] Data/hora do início do incidente
    - [ ] Data/hora da resolução
    - [ ] Causa raiz identificada
    - [ ] Ações corretivas tomadas
    - [ ] Impacto (usuários afetados, duração)
    - [ ] Ações preventivas para evitar recorrência

!!! tip "Template de registro"
    ```
    **Incidente:** INC-YYYYMMDD-XXX
    **Data:** YYYY-MM-DD HH:MM ~ HH:MM
    **Causa:** [descrever]
    **Resolução:** [descrever]
    **Prevenção:** [descrever]
    ```

---

!!! tip "Runbook atualizado em 2026-08-25"
    Versão: 1.0 | Autor: Time de Redes
