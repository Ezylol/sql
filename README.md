# SQL - Manutenção Industrial SENAI

Este repositório contém a versão funcional principal do banco de dados para o projeto de manutenção industrial.

## Estrutura

- `schema.sql`: cria o banco e todas as tabelas do projeto.
- `seed.sql`: insere os dados iniciais de exemplo.

## Como executar

No terminal, em uma máquina com MySQL 8.0.16+:

```bash
mysql -u seu_usuario -p < schema.sql
mysql -u seu_usuario -p < seed.sql
```

Ou dentro do cliente MySQL:

```sql
SOURCE schema.sql;
SOURCE seed.sql;
```

## Banco criado

O script `schema.sql` cria automaticamente o banco `manutencao_industrial` e o seleciona para uso.

## Observação

As versões alternativas foram removidas do fluxo principal e não fazem parte da execução funcional do projeto. A versão atual é a principal e está pronta para uso.
