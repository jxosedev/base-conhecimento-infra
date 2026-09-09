---
title: Conta AWS
description: Organizacao, contas e servicos utilizados na AWS
---

# :material-aws: Conta AWS

!!! info "Ambiente AWS"
    Documentacao das contas, regioes e servicos utilizados na Amazon Web Services.

---

## Organizacao de Contas

| Conta | ID | Ambiente | Responsavel |
|-------|-----|----------|-------------|
| `infra-management` | `1111-2222-3333` | Gestao / Billing | Infra |
| `infra-producao` | `4444-5555-6666` | Producao | Infra |
| `infra-homolog` | `7777-8888-9999` | Homologacao | Infra |

!!! warning "Acesso"
    O acesso e feito exclusivamente via **AWS SSO** (IAM Identity Center).
    Nao existem usuarios IAM de longa duracao com chaves de acesso ativas.

---

## Regiao Padrao

| Item | Valor |
|------|-------|
| Regiao primaria | `sa-east-1` (Sao Paulo) |
| Regiao de DR | `us-east-1` (Norte da Virginia) |

---

## Servicos Utilizados

| Servico | Uso |
|---------|-----|
| :material-server: EC2 | Instancias de aplicacao e runners |
| :material-database: RDS | Banco de dados gerenciado (replica) |
| :material-bucket: S3 | Backups, artefatos e assets estaticos |
| :material-dns: Route 53 | DNS dos dominios corporativos |
| :material-shield: CloudFront + WAF | CDN e protecao de borda |
| :material-key: Secrets Manager | Segredos de aplicacao |
| :material-chart-line: CloudWatch | Metricas e alarmes |

---

## Boas Praticas

- [x] MFA obrigatorio para todos os usuarios via SSO
- [x] Buckets S3 privados por padrao (block public access)
- [x] Tags obrigatorias: `ambiente`, `time`, `centro-custo`
- [x] CloudTrail habilitado em todas as contas

---

## Ver Tambem

- [Politica de Custos](politica-custos.md)
- [Conta GCP](gcp.md)
- [Politica de Backup](../../politicas/backup.md)
