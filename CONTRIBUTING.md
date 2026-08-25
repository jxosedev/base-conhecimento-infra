# Como Contribuir com a Base de Conhecimento

## Fluxo Rapido

1. Abra um **issue** usando o template adequado
2. Crie uma **branch** a partir de `master`
3. Copie o **template** mais proximo de `docs/assets/templates/`
4. Preencha o conteudo
5. Teste localmente com `mkdocs serve`
6. Abra um **Pull Request**
7. Aguarde revisao de 1 membro do time

## Regras

- **Nunca** expor senhas, tokens ou credenciais
- Usar os templates de admonitions do Material Theme
- Indicar linguagem nos blocos de codigo
- Manter formatacao consistente

## Estrutura de Pastas

```
docs/
├── guia/                    # Guia de uso da base
├── infra/
│   ├── servidores/          # Documentacao de servidores
│   ├── rede/                # Docs de rede
│   ├── armazenamento/       # Storage
│   └── cloud/               # AWS/GCP/Azure
├── runbooks/
│   ├── incidentes/          # Resposta a incidentes
│   ├── manutencoes/         # Manutencoes preventivas
│   └── backups/             # Procedimentos de backup
├── pop/                     # Procedimentos operacionais
└── politicas/               # Politicas e diretrizes
```

## Comandos Uteis

```bash
# Rodar localmente
mkdocs serve

# Build de producao
mkdocs build

# Publicar alteracoes
mkdocs gh-deploy --force
```
