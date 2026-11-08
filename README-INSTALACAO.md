# Linha do Dia — Financeiro pessoal (cópia independente)

Esta é uma instalação nova e independente do Linha do Dia.

- PF somente: não existe aba PJ.
- Banco PostgreSQL próprio.
- URL própria no Railway.
- Nenhum dado é compartilhado com a instalação original.
- A interface inclui fluxo anual, lançamentos, realizado/provisionado, orçamentos, recorrências, reservas e investimentos.
- Categorias podem ser desativadas/excluídas sem apagar os lançamentos históricos.

## Arquivos do repositório

```text
/
├── .gitignore
├── db.js
├── package.json
├── schema.sql
├── server.js
└── public/
    └── index.html
```

## Instalação

### 1. GitHub

Crie um repositório NOVO, por exemplo `linha-do-dia-financeiro`.

Faça upload de todos os arquivos deste pacote mantendo a pasta `public` e o arquivo `public/index.html` dentro dela.

Não envie estes arquivos para o repositório do seu Linha do Dia atual.

### 2. Railway — projeto novo

No Railway, crie um **New Project > Empty Project**. Use um nome diferente do seu projeto atual.

Dentro desse novo projeto, clique em **+ New** e adicione **PostgreSQL**.

Depois adicione um segundo serviço no MESMO projeto, conectando o novo repositório do GitHub.

### 3. DATABASE_URL

Abra o serviço da aplicação (o que está conectado ao GitHub), vá em **Variables** e crie:

```text
DATABASE_URL=${{Postgres.DATABASE_URL}}
```

Se o serviço PostgreSQL tiver outro nome no Railway, use exatamente esse nome no lugar de `Postgres`.

**Não copie a DATABASE_URL do seu Linha do Dia.** A separação dos bancos é o que garante que os dados dele não se misturem aos seus.

Depois aplique/deploy as alterações pendentes.

### 4. URL própria

Quando o deploy estiver com status de sucesso:

1. Abra o serviço da aplicação.
2. Vá em **Settings**.
3. Em **Networking > Public Networking**, clique em **Generate Domain**.
4. O Railway criará uma URL própria `*.up.railway.app`.

É essa URL que deve ser enviada ao seu amigo.

## Primeiro acesso

No primeiro deploy, `schema.sql` cria automaticamente as tabelas no PostgreSQL novo. Não é necessário executar SQL manualmente.

O banco começa vazio. As categorias pessoais iniciais e os três destinos da área “Guardar” são criados automaticamente.

## Importante

A URL da cópia e o banco da cópia são independentes da sua instalação atual. O amigo não recebe acesso ao projeto, repositório ou banco original apenas por usar a nova URL.
