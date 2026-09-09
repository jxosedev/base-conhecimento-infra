---
title: Conta GCP
description: Projetos e servicos utilizados no Google Cloud Platform
---

# :material-google-cloud: Conta GCP

!!! info "Ambiente GCP"
    Documentacao dos projetos e servicos utilizados no Google Cloud Platform.

---

## Projetos

| Projeto | ID | Ambiente | Responsavel |
|---------|-----|----------|-------------|
| `infra-prod` | `infra-prod-01` | Producao | Infra |
| `infra-analytics` | `infra-analytics-01` | Analytics / BigQuery | Dados |

!!! warning "Acesso"
    Acesso via **Google Cloud Identity** com grupos. Contas de servico
    (service accounts) usam Workload Identity sempre que possivel, evitando
    chaves `.json` de longa duracao.

---

## Regiao Padrao

| Item | Valor |
|------|-------|
| Regiao primaria | `southamerica-east1` (Sao Paulo) |
| Multi-regiao de storage | `SOUTHAMERICA` |

---

## Servicos Utilizados

| Servico | Uso |
|---------|-----|
| :material-google-cloud: Compute Engine | VMs de workloads especificos |
| :material-database: BigQuery | Data warehouse e analytics |
| :material-bucket: Cloud Storage | Data lake e exports |
| :material-key: Secret Manager | Segredos de aplicacao |
| :material-chart-line: Cloud Monitoring | Metricas e alertas |

---

## Boas Praticas

- [x] MFA obrigatorio via Google Identity
- [x] Buckets privados por padrao (uniform bucket-level access)
- [x] Labels obrigatorias: `ambiente`, `time`, `centro-custo`
- [x] Audit Logs habilitados

---

## Ver Tambem

- [Politica de Custos](politica-custos.md)
- [Conta AWS](aws.md)
