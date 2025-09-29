# GitFlow CI

Este repositório contém um workflow de CI/CD para automatizar o fluxo GitFlow.

## Padrão de Branches

- `feature/nome-da-feature` ou `feat/nome-da-feature`: Desenvolvimento de novas funcionalidades
- `bugfix/nome-do-bug` ou `fix/nome-do-bug`: Correção de bugs
- `release/X.Y.Z`: Preparação para lançamento (ex: `release/1.0.0`)
- `hotfix/X.Y.Z`: Correções urgentes em produção

## Fluxo de Trabalho

1. **Features e Bugfixes**:
   - Devem ser criados a partir da branch de desenvolvimento (`dev` ou `development`)
   - Após conclusão, são mesclados de volta para a branch de desenvolvimento

2. **Releases**:
   - Criadas a partir da branch de desenvolvimento
   - Após aprovação, são mescladas na `main`
   - Após o merge na `main`, a `main` é sincronizada de volta para a branch de desenvolvimento

3. **Hotfixes**:
   - Criados a partir da `main`
   - Após aprovação, são mesclados na `main`
   - Após o merge na `main`, a `main` é sincronizada de volta para a branch de desenvolvimento

## Configuração do Ambiente

O workflow de CI/CD configura automaticamente o ambiente Git para realizar operações como merge, push e criação de tags. A configuração inclui:

```bash
git config --global user.name 'GitHub Actions'
git config --global user.email 'actions@github.com'
```

Esta configuração é necessária para que o Git possa identificar o autor das alterações realizadas pelo workflow.

## Requisitos

- GitHub Actions habilitado no repositório
- Permissões adequadas para o token do GitHub Actions
