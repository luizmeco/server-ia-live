# ASK-LIVE-IA Server

API REST desenvolvida em Node.js com TypeScript para o projeto ASK-LIVE-IA.

## 🛠️ Tecnologias

### Core
- **Node.js** - Runtime JavaScript
- **TypeScript** - Linguagem de programação
- **Fastify** - Framework web rápido
- **Drizzle ORM** - ORM para PostgreSQL
- **PostgreSQL** - Banco de dados (com pgvector para vetores)

### Validação e Tipagem
- **Zod** - Validação de schemas
- **fastify-type-provider-zod** - Integração Zod com Fastify

### Desenvolvimento
- **Biome** - Linter e formatter
- **Drizzle Kit** - Ferramentas para migrações
- **Docker Compose** - Containerização do banco

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts    # Conexão com banco
│   ├── schema/          # Schemas do Drizzle
│   └── migrations/      # Migrações do banco
├── http/
│   └── routes/          # Rotas da API
├── env.ts              # Configuração de variáveis
└── server.ts           # Servidor principal
```

## 🚀 Setup

### Pré-requisitos
- Node.js 18+
- Docker e Docker Compose
- PostgreSQL (via Docker)

### Instalação

1. **Clone e instale dependências**
```bash
npm install
```

2. **Configure variáveis de ambiente**
```bash
# Crie um arquivo .env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

3. **Suba o banco de dados**
```bash
docker-compose up -d
```

4. **Execute migrações**
```bash
npx drizzle-kit push
```

5. **Inicie o servidor**
```bash
# Desenvolvimento
npm run dev

# Produção
npm start
```

## 📋 Scripts Disponíveis

- `npm run dev` - Servidor em modo desenvolvimento com hot reload
- `npm start` - Servidor em produção
- `npm run db:seed` - Executa seed do banco de dados

## 🔧 Padrões de Projeto

- **TypeScript** - Tipagem estática
- **ES Modules** - Import/export moderno
- **Schema Validation** - Validação com Zod
- **ORM** - Drizzle ORM para queries type-safe
- **CORS** - Configurado para permitir todas as origens
- **Environment Variables** - Validação com Zod

## 📡 Endpoints

- `GET /health` - Health check
- `GET /rooms` - Lista salas disponíveis

## 🗄️ Banco de Dados

- **PostgreSQL** com extensão pgvector
- **Drizzle ORM** para queries type-safe
- **Migrações** automáticas com Drizzle Kit
- **Snake case** para nomes de tabelas/colunas 