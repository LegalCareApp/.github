# LegalCareApp

[![CI Backend](https://github.com/LegalCareApp/legalcare/actions/workflows/ci-backend.yml/badge.svg)](https://github.com/LegalCareApp/legalcare/actions/workflows/ci-backend.yml)
[![Contract Tests](https://github.com/LegalCareApp/legalcare/actions/workflows/backend-contract-tests.yml/badge.svg)](https://github.com/LegalCareApp/legalcare/actions/workflows/backend-contract-tests.yml)
[![Integrations Tests](https://github.com/LegalCareApp/legalcare/actions/workflows/integrations-contract-tests.yml/badge.svg)](https://github.com/LegalCareApp/legalcare/actions/workflows/integrations-contract-tests.yml)

Monorepo do LegalCareApp com backend NestJS/Prisma, app mobile Expo/React Native, design-system e integrações.

📚 [Documentação da API](./docs/functional-spec.md) | 📊 [Matriz de Cobertura](./docs/coverage-matrix.md) | 📝 [Changelog](./docs/api-changelog.md) | 📅 [Sprint 01](./docs/sprints/sprint-01-produto-api.md)

## Stack principal

- Backend: NestJS, TypeScript, Prisma e PostgreSQL
- Mobile: Expo, React Native e Expo Router
- Design System: React, Tailwind e componentes compartilhados

## Requisitos

- Node.js 22.x
- npm 11.x
- Docker, para subir PostgreSQL local no Codespaces/desenvolvimento

> O backend declara suporte para Node `>=22.0.0 <23.0.0`. Se o Codespaces abrir com Node 24, execute `nvm use` na raiz do repositório.

## Setup rápido no Codespaces

### 1. Usar Node 22

```bash
nvm install
nvm use
node -v
```

### 2. Criar o `.env` do backend

```bash
cp backend/.env.example backend/.env
```

O arquivo `backend/.env.example` já contém uma `DATABASE_URL` local compatível com o `docker-compose.yml` deste repositório:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/legalcare?schema=public"
```

Nunca versionar `backend/.env`.

### 3. Subir PostgreSQL local

```bash
docker compose up -d db
```

### 4. Instalar dependências do backend e preparar Prisma

```bash
npm run backend:install
npm run backend:prisma:generate
npm run backend:prisma:migrate
```

Se preferir rodar dentro da pasta do backend:

```bash
cd backend
npm install
npx prisma generate
npx prisma migrate dev
```

### 5. Rodar backend

Pela raiz:

```bash
npm run backend:dev
```

Ou dentro de `backend/`:

```bash
npm run start:dev
```

API padrão: `http://localhost:3000`.

### 6. Rodar app mobile/web

Pela raiz:

```bash
npm run mobile:install
npm run web
```

Ou dentro de `mobile/`:

```bash
cd mobile
npm install
npm run web
```

## Scripts úteis da raiz

```bash
npm run backend:install
npm run backend:dev
npm run backend:build
npm run backend:test
npm run backend:test:contracts
npm run backend:prisma:generate
npm run backend:prisma:migrate
npm run mobile:install
npm run mobile:start
npm run mobile:web
npm run web
```

## Baseline pré Sprint 01 Produto/API

A base corrigida para iniciar a Sprint 01 remove artefatos gerados do pacote, ajusta host `0.0.0.0` para Codespaces/containers, ativa o módulo de notificações no backend e inclui uma migration inicial para `Notification`/`PushToken`.

Validação recomendada:

```bash
npm run install:all
docker compose up -d db
npm run backend:prisma:generate
npm run backend:prisma:migrate
npm run backend:build
npm run web:build
```

Detalhes: [`docs/BASELINE-SP1.md`](docs/BASELINE-SP1.md).

## Checkout / Invoices SP2-006

Contrato principal:

- `GET /invoices` lista cobranças do usuário autenticado.
- `GET /invoices?status=OPEN` filtra por status.
- `GET /invoices/:id` retorna detalhe da cobrança.
- `POST /invoices/:id/checkout` inicia pagamento.
- `GET /invoices/:id/status` permite polling.
- `GET /invoices/summary` retorna resumo financeiro.

Status mínimos da jornada:

- `OPEN`
- `PROCESSING`
- `PAID`
- `OVERDUE`
- `CANCELED`

Usuários comuns só acessam suas próprias invoices. Usuários `ADMIN` podem consultar todas.


## SP1-001 — Auth v2

Contrato implementado em `docs/api-contracts/auth-v2.md`.

Endpoints:

- `POST /auth/login`
- `POST /auth/refresh`

Validação:

```bash
npm run backend:test:contracts
```


### SP1-002 — Cases + timeline

Contrato `cases.v2` disponível em `docs/api-contracts/cases-v2.md` com lista, detalhe, timeline e escopo por papel.


### SP1-003 — Eventos processuais

Pacote atualizado com validação de eventos processuais:

- `POST /cases/:id/events` aceita eventos `INFO`, `PROGRESS`, `DOCUMENT`, `BILLING` e `STATUS_CHANGE`.
- Eventos `DOCUMENT` exigem `documentIds`.
- Anexos ficam rastreáveis via `Document.caseEventId`.
- Transições de status são validadas antes de atualizar o processo.
- Contrato: `docs/api-contracts/case-events-v2.md`.


### SP1-004 — Financeiro v2

Contrato financeiro canônico: `docs/api-contracts/finance-v2.md`.

Endpoints principais:

- `GET /invoices`
- `GET /invoices/:id`
- `POST /invoices/:id/checkout`
- `GET /invoices/:id/status`
- `POST /invoices/:id/payment-confirmation`

Repetir confirmação de pagamento com a mesma chave idempotente retorna replay sem duplicar a baixa financeira.


### SP1-005 — Profile v2

Contrato de perfil e credenciais: `docs/api-contracts/profile-v2.md`.

Endpoints principais:

- `GET /users/me`
- `PATCH /users/me`
- `POST /users/me/avatar`
- `POST /users/me/change-password`

As respostas incluem `sessionUser` para que Web e Mobile reflitam imediatamente alterações de perfil na sessão. Senha antiga incorreta retorna `INVALID_CURRENT_PASSWORD`; conflitos únicos retornam códigos específicos para e-mail, CPF e OAB.

---

## 📚 Documentação

### API e Contratos
- [Especificação Funcional](./docs/functional-spec.md) — documentação completa de todos os endpoints
- [Matriz de Cobertura](./docs/coverage-matrix.md) — status de implementação por endpoint
- [Changelog da API](./docs/api-changelog.md) — histórico de mudanças e breaking changes
- [Contratos de API](./docs/api-contracts/) — documentação detalhada por versão

### Sprints
- [Sprint 01 — Produto/API](./docs/sprints/sprint-01-produto-api.md) — resumo da sprint com entregas

### Guias
- [Guia de Páginas](./docs/pages-guide.md) — mapeamento de telas Web/Mobile
- [Checklist de Release](./docs/release-readiness-checklist.md) — preparação para release
- [Arquitetura](./architecture.md) — visão geral da arquitetura do sistema

---

## 🔗 Endpoints Principais (Sprint 01)

| Módulo | Endpoint | Descrição |
|--------|----------|-----------|
| **Auth** | `POST /auth/login` | Login com JWT |
| **Cases** | `GET /cases` | Lista de casos com paginação |
| **Invoices** | `POST /invoices/:id/checkout` | Checkout com idempotência |
| **Profile** | `PATCH /users/me` | Atualização de perfil |
| **Notifications** | `GET /notifications` | Lista com unreadCount |
| **Integrations** | `POST /stripe/checkout` | Mock de pagamento |

Para exemplos completos de request/response, consulte a [Especificação Funcional](./docs/functional-spec.md).
