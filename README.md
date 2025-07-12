
# NLW Pocket

O NLW Pocket é um projeto desenvolvido durante a Next Level Week (NLW), um evento online da [Rocketseat](https://www.rocketseat.com.br/).

O in.orbit é uma aplicação de gerenciamento de metas diárias, permitindo que os usuários criem metas, acompanhem o progresso e visualizem um resumo semanal.

<img src="web/public/home.png" />
<img src="web/public/cadastro.png" />
<img src="web/public/metas.png" />

## 🚀 Tecnologias Utilizadas

Este projeto é dividido em duas partes principais: o backend (`server`) e o frontend (`web`).

### Backend (Server)

- **Node.js**: Ambiente de execução JavaScript no servidor.
- **Fastify**: Framework web de alta performance e baixo overhead.
- **TypeScript**: Superset do JavaScript que adiciona tipagem estática.
- **Drizzle ORM**: ORM "headless" para TypeScript, utilizado para a comunicação com o banco de dados.
- **PostgreSQL**: Banco de dados relacional.
- **Zod**: Biblioteca para validação de esquemas e tipos.
- **Docker**: Utilizado para criar um ambiente de desenvolvimento com o PostgreSQL.
- **Biome**: Ferramenta para formatação e linting do código.

### Frontend (Web)

- **React**: Biblioteca para construção de interfaces de usuário.
- **Vite**: Ferramenta de build e desenvolvimento frontend extremamente rápida.
- **TypeScript**: Linguagem de programação principal.
- **Tailwind CSS**: Framework de CSS utilitário para estilização.
- **shadcn/ui**: Metodologia para criação de componentes de UI reutilizáveis, utilizando Radix UI e Tailwind CSS.
- **TanStack Query**: Biblioteca para data fetching, cache e gerenciamento de estado assíncrono.
- **React Hook Form & Zod**: Para construção e validação de formulários.
- **Biome**: Ferramenta para formatação e linting do código.

## ⚙️ Setup e Configuração

Siga os passos abaixo para executar o projeto em seu ambiente local.

### Pré-requisitos

- [Node.js](https://nodejs.org/en/) (v18 ou superior)
- [Docker](https://www.docker.com/products/docker-desktop/) e Docker Compose

### 1. Clonar o Repositório

```bash
git clone https://github.com/ricardoof/inorbit.git
cd inorbit
```

### 2. Configuração do Backend

Primeiro, vamos configurar e executar o servidor.

```bash
# 1. Navegue até a pasta do servidor
cd server

# 2. Crie o arquivo de variáveis de ambiente
# Crie um arquivo chamado .env na raiz da pasta /server e adicione o seguinte conteúdo:
# DATABASE_URL="postgresql://docker:docker@localhost:5432/inorbit?schema=public"

# 3. Instale as dependências
npm install

# 4. Inicie o container do PostgreSQL com Docker
docker-compose up -d

# 5. Execute as migrações do banco de dados
npx drizzle-kit migrate:pg

# 6. (Opcional) Popule o banco com dados de teste
npm run seed

# 7. Inicie o servidor de desenvolvimento
npm run dev
```

O servidor backend estará disponível em `http://localhost:3333`.

### 3. Configuração do Frontend

Com o backend em execução, vamos configurar o frontend em um novo terminal.

```bash
# 1. Navegue até a pasta do frontend (a partir da raiz do projeto)
cd web

# 2. Instale as dependências
npm install

# 3. Inicie o servidor de desenvolvimento
npm run dev
```

A aplicação web estará disponível em `http://localhost:5173`. 