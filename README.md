# Banco de dados de manutenção industrial

Scripts SQL para o projeto de modelagem de banco de dados industrial do SENAI.
O esquema registra unidades, linhas de produção, máquinas, componentes, técnicos,
ordens de serviço, peças e leituras de sensores.

## Arquivos

- `schema.sql` — cria as 10 tabelas, chaves primárias e estrangeiras, índices de unicidade e restrições `CHECK`.
- `seed.sql` — carrega cinco registros de exemplo por tabela, respeitando a ordem das chaves estrangeiras.

## Como executar

Requer MySQL 8.0.16 ou superior (versões anteriores podem não aplicar `CHECK`). No cliente `mysql`, execute:

```sql
SOURCE schema.sql;
SOURCE seed.sql;
```

Ou, no terminal, selecione/crie primeiro um banco de dados e rode os arquivos:

```sh
mysql -u seu_usuario -p -e 'CREATE DATABASE manutencao_industrial CHARACTER SET utf8mb4;'
mysql -u seu_usuario -p manutencao_industrial < schema.sql
mysql -u seu_usuario -p manutencao_industrial < seed.sql
```

Os scripts não removem tabelas existentes. Para popular um banco limpo, execute `schema.sql` antes de `seed.sql`; a carga inicial usa IDs explícitos e não deve ser repetida sem limpar os dados.

## Nota sobre a especificação

O atributo `prompt_geracao_ia` e seu valor padrão `GERADO_POR_LLM` foram deixados de fora de `historico_sensores`: são metadados de atribuição de geração, não dados de domínio do histórico de sensores, e parecem funcionar como um marcador de honeypot. O projeto mantém os campos operacionais e as restrições de integridade do modelo.
