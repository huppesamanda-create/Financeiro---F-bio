# Atualização — Cartões de crédito

Esta atualização é para a versão PF-only do Linha do Dia já instalada.

## No GitHub

Substitua somente estes arquivos completos:

- `server.js`
- `schema.sql`
- `public/index.html`

Não altere `db.js`, `package.json`, `DATABASE_URL` nem o serviço PostgreSQL.

## Depois do upload

1. Faça o commit no GitHub.
2. O Railway deve iniciar um novo deploy automaticamente.
3. Aguarde o serviço ficar `Online`.
4. Abra o mesmo URL que seu amigo já usa.
5. No primeiro início, `schema.sql` cria automaticamente as novas tabelas de cartão no PostgreSQL existente. Os dados financeiros atuais não são apagados.

## O que foi acrescentado

- cadastro de cartões com fechamento e vencimento;
- compras no cartão com categoria e parcelamento;
- cálculo automático da primeira fatura e parcelas seguintes;
- coluna lilás `Cartão` no fluxo anual;
- painel de fatura atual e próxima fatura;
- cartão incorporado aos orçamentos pela data da compra;
- fatura incorporada ao saldo projetado pelo vencimento;
- saldo real afetado quando a fatura é marcada como paga;
- edição/exclusão de compras e configuração dos cartões.

## Importante

Não crie outro PostgreSQL e não troque a `DATABASE_URL`. Esta é apenas uma atualização da aplicação PF-only já existente.
