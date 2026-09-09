---
title: Politica de Custos
description: Diretrizes de controle e otimizacao de custos em cloud
---

# :material-cash-multiple: Politica de Custos

!!! info "FinOps"
    Diretrizes para controle, previsibilidade e otimizacao de custos nos
    ambientes de cloud (AWS e GCP).

---

## Orcamento e Alertas

| Ambiente | Orcamento Mensal | Alerta em |
|----------|------------------|-----------|
| Producao | R$ 25.000 | 70% / 90% / 100% |
| Homologacao | R$ 5.000 | 80% / 100% |
| Analytics | R$ 8.000 | 80% / 100% |

!!! warning "Estouro de orcamento"
    Ao atingir **90%** do orcamento, o canal `#infra-custos` e notificado
    automaticamente. Estouros exigem justificativa registrada em issue.

---

## Regras Obrigatorias

- [x] Todo recurso deve ter as tags/labels: `ambiente`, `time`, `centro-custo`
- [x] Recursos sem tag sao candidatos a desligamento apos 7 dias
- [x] Ambientes de homologacao sao desligados fora do horario comercial
- [x] Snapshots e volumes orfaos sao removidos mensalmente

---

## Otimizacoes Recorrentes

| Acao | Frequencia | Responsavel |
|------|------------|-------------|
| Revisar recursos ociosos | Mensal | Infra |
| Revisar Savings Plans / CUDs | Trimestral | Infra |
| Limpar snapshots antigos | Mensal | Infra |
| Revisar classes de storage S3/GCS | Trimestral | Infra |

---

## Ferramentas

| Ferramenta | Uso |
|------------|-----|
| AWS Cost Explorer | Analise de custos AWS |
| GCP Billing Reports | Analise de custos GCP |
| Budgets & Alerts | Alertas automaticos |

---

## Ver Tambem

- [Conta AWS](aws.md)
- [Conta GCP](gcp.md)
