ï»¿# Rotax1 - Plataforma de Entregas êÅ¡ltima Milha

<div align="center">

![Rotax1 Logo](doc/logo-Rotax1.png)

**Plataforma moderna de entregas sob demanda especializada em nichos verticais**

[![TypeScript](https://img.shields.io/badge/TypeScript-5.3-blue.svg)](https://www.typescriptlang.org/)
[![Fastify](https://img.shields.io/badge/Fastify-4.25-green.svg)](https://www.fastify.io/)
[![Prisma](https://img.shields.io/badge/Prisma-5.7-purple.svg)](https://www.prisma.io/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue.svg)](https://www.postgresql.org/)
[![License](https://img.shields.io/badge/License-Private-red.svg)]()

</div>

---

## VisêÂ£o Geral

**Rotax1** êÂ© uma plataforma de entregas êÂºltima milha que conecta clientes, entregadores e transportadoras em um ecossistema integrado. O diferencial êÂ© a especializaêÂ§êÂ£o em nichos verticais com requisitos especêÂ­ficos de manuseio e entrega.

### Nicho Inicial: Medicamentos VeterinêÂ¡rios

O mercado pet brasileiro representa **R$ 52 bilhêÂµes** com crescimento de 14% ao ano. ClêÂ­nicas veterinêÂ¡rias e pet shops enfrentam desafios êÂºnicos:

- Medicamentos que requerem temperatura controlada
- UrgêÂªncia em entregas de emergêÂªncia
- Necessidade de rastreamento em tempo real
- Conformidade com regulamentaêÂ§êÂµes sanitêÂ¡rias

### Problema Resolvido

1. **Para Clientes**: Dificuldade em obter entregas rêÂ¡pidas e confiêÂ¡veis para produtos veterinêÂ¡rios
2. **Para Entregadores**: Falta de plataformas especializadas com demanda constante
3. **Para Transportadoras**: AusêÂªncia de sistema integrado para receber demandas excedentes

---

## Arquitetura

### Stack TecnolêÂ³gico

| Camada | Tecnologia |
|--------|------------|
| **Backend** | Node.js + Fastify + TypeScript |
| **Banco de Dados** | PostgreSQL + PostGIS (geolocalizaêÂ§êÂ£o) |
| **ORM** | Prisma |
| **Cache/Real-time** | Redis + Socket.IO |
| **Mobile** | React Native (Expo) |
| **Web (Cliente/Admin)** | Next.js 14 |
| **Pagamentos** | Mercado Pago (Pix) |
| **Mapas** | Google Maps API |
| **Push Notifications** | Firebase Cloud Messaging |

### Estrutura do Monorepo

```
rotax1/
ê¢âÅê¢ââ¬ê¢ââ¬ apps/
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ api/                 # API REST (Fastify)
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ src/
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ common/      # Config, errors, middlewares
ê¢ââ   ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ modules/     # MêÂ³dulos de feature (auth, orders, etc.)
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ mobile/              # App React Native (Cliente + Entregador)
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ web/                 # Portal do Cliente (Next.js)
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ admin/               # Painel Administrativo (Next.js)
ê¢âÅê¢ââ¬ê¢ââ¬ packages/
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ database/            # Prisma schema e migraêÂ§êÂµes
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ shared/              # Tipos e validaêÂ§êÂµes compartilhados
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ui/                  # Componentes UI compartilhados
ê¢ââê¢ââ¬ê¢ââ¬ infrastructure/
    ê¢ââê¢ââ¬ê¢ââ¬ docker/              # Docker Compose para dev local
```

---

## Funcionalidades Principais

### Para Clientes
- Cadastro e autenticaêÂ§êÂ£o via email/telefone
- SolicitaêÂ§êÂ£o de entregas com mêÂºltiplos endereêÂ§os
- CêÂ¡lculo de preêÂ§o em tempo real baseado em distêÂ¢ncia
- Pagamento via Pix (integraêÂ§êÂ£o Mercado Pago)
- Rastreamento em tempo real do entregador
- HistêÂ³rico de pedidos e avaliaêÂ§êÂµes
- NotificaêÂ§êÂµes push de status

### Para Entregadores
- Cadastro com validaêÂ§êÂ£o de documentos (CNH, veêÂ­culo)
- VisualizaêÂ§êÂ£o de pedidos disponêÂ­veis na regiêÂ£o
- Aceite/rejeiêÂ§êÂ£o de corridas
- NavegaêÂ§êÂ£o integrada (Google Maps)
- ComprovaêÂ§êÂ£o de entrega com foto
- Dashboard de ganhos
- Toggle online/offline

### Para Administradores
- GestêÂ£o de usuêÂ¡rios (clientes, entregadores, transportadoras)
- AprovaêÂ§êÂ£o de cadastros de entregadores
- Monitoramento de pedidos em tempo real
- RelatêÂ³rios financeiros e operacionais
- ConfiguraêÂ§êÂ£o de taxas e comissêÂµes
- GestêÂ£o de regiêÂµes de atendimento

---

## Como Rodar o Projeto

### PrêÂ©-requisitos

- Node.js 20+
- pnpm 8+
- Docker (para banco de dados local)

### Setup

```bash
# Clone o repositêÂ³rio
git clone git@github.com:linnoff88-dev/RotaX1.git
cd RotaX1

# Instale as dependêÂªncias
pnpm install

# Configure as variêÂ¡veis de ambiente
cp .env.example .env

# Inicie o banco de dados local
cd infrastructure/docker
docker-compose up -d
cd ../..

# Gere o cliente Prisma
pnpm db:generate

# Rode as migraêÂ§êÂµes
pnpm db:migrate

# Popule o banco com dados de teste
pnpm db:seed

# Inicie o servidor de desenvolvimento
pnpm dev
```

### Comandos DisponêÂ­veis

| Comando | DescriêÂ§êÂ£o |
|---------|-----------|
| `pnpm dev` | Inicia todos os apps em modo desenvolvimento |
| `pnpm build` | Compila todos os pacotes |
| `pnpm lint` | Executa o linter em todos os pacotes |
| `pnpm test` | Roda os testes |
| `pnpm db:generate` | Gera o cliente Prisma |
| `pnpm db:migrate` | Executa migraêÂ§êÂµes do banco |
| `pnpm db:seed` | Popula o banco com dados de teste |
| `pnpm db:studio` | Abre o Prisma Studio |

---

## VariêÂ¡veis de Ambiente

```bash
# Database (Supabase ou PostgreSQL local)
DATABASE_URL="postgresql://postgres:password@localhost:5432/rotax1"

# Redis
REDIS_URL="redis://localhost:6379"

# JWT
JWT_SECRET="sua-chave-secreta-minimo-32-caracteres"
JWT_REFRESH_SECRET="sua-chave-refresh-minimo-32-caracteres"

# Google Maps
GOOGLE_MAPS_API_KEY="sua-api-key"

# Mercado Pago
MERCADO_PAGO_ACCESS_TOKEN="seu-token"
MERCADO_PAGO_WEBHOOK_SECRET="seu-secret"

# Firebase
FIREBASE_PROJECT_ID="seu-projeto"
FIREBASE_PRIVATE_KEY="sua-chave"
FIREBASE_CLIENT_EMAIL="seu-email"
```

---

## API Endpoints

### AutenticaêÂ§êÂ£o

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| POST | `/auth/register` | Cadastro de novo usuêÂ¡rio |
| POST | `/auth/login` | Login (retorna JWT) |
| POST | `/auth/refresh` | Renova access token |
| GET | `/auth/me` | Dados do usuêÂ¡rio autenticado |

### Clientes

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| GET | `/clients/profile` | Perfil do cliente |
| PATCH | `/clients/profile` | Atualiza perfil |
| POST | `/clients/profile/photo` | Upload foto de perfil |
| GET | `/clients/addresses` | Lista endereêÂ§os |
| POST | `/clients/addresses` | Adiciona endereêÂ§o |
| PATCH | `/clients/addresses/:id` | Atualiza endereêÂ§o |
| DELETE | `/clients/addresses/:id` | Remove endereêÂ§o |

### FarmêÂ¡cias

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| GET | `/pharmacies` | Busca farmêÂ¡cias |
| GET | `/pharmacies/:id` | Detalhes da farmêÂ¡cia |
| GET | `/pharmacies/nearby` | FarmêÂ¡cias prêÂ³ximas |

### Pedidos (Cliente)

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| POST | `/orders/calculate-price` | Calcula preêÂ§o |
| POST | `/orders` | Cria pedido |
| GET | `/orders/:id` | Detalhes do pedido |
| GET | `/orders/:id/track` | Rastrear pedido |
| GET | `/orders/history` | HistêÂ³rico de pedidos |
| POST | `/orders/:id/cancel` | Cancela pedido |
| POST | `/orders/:id/rate` | Avalia pedido |

### Motoristas

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| GET | `/drivers/profile` | Perfil do motorista |
| PATCH | `/drivers/profile` | Atualiza perfil |
| POST | `/drivers/documents` | Upload documento |
| POST | `/drivers/availability` | Toggle online/offline |
| POST | `/drivers/location` | Atualiza localizaêÂ§êÂ£o |
| GET | `/drivers/orders/available` | Pedidos disponêÂ­veis |
| POST | `/drivers/orders/accept` | Aceita pedido |
| GET | `/drivers/orders/current` | Pedido atual |
| POST | `/drivers/orders/:id/pickup` | Confirma coleta |
| POST | `/drivers/orders/:id/deliver` | Confirma entrega |
| GET | `/drivers/earnings` | Ganhos |

### Admin

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| GET | `/admin/dashboard` | Dashboard KPIs |
| GET | `/admin/users` | Lista usuêÂ¡rios |
| PATCH | `/admin/users/:id/status` | Bloqueia/desbloqueia |
| GET | `/admin/drivers/pending` | Motoristas pendentes |
| POST | `/admin/drivers/:id/approve` | Aprova/rejeita motorista |
| GET | `/admin/orders` | Lista pedidos |
| POST | `/admin/orders/:id/cancel` | Cancela pedido |
| POST | `/admin/orders/:id/reassign` | Reatribui motorista |
| GET | `/admin/financial/report` | RelatêÂ³rio financeiro |
| GET | `/admin/financial/payouts` | Lista repasses |
| POST | `/admin/financial/payouts/process` | Processa repasses |

### Health Check

| MêÂ©todo | Endpoint | DescriêÂ§êÂ£o |
|--------|----------|-----------|
| GET | `/health` | Status da API |
| GET | `/docs` | DocumentaêÂ§êÂ£o Swagger |

---

## Modelo de Dados

### Entidades Principais

```
User (usuêÂ¡rio base)
ê¢âÅê¢ââ¬ê¢ââ¬ Client (cliente - solicita entregas)
ê¢âÅê¢ââ¬ê¢ââ¬ Driver (entregador - realiza entregas)
ê¢âÅê¢ââ¬ê¢ââ¬ Carrier (transportadora - recebe demanda excedente)
ê¢ââê¢ââ¬ê¢ââ¬ Admin (administrador)

Order (pedido)
ê¢âÅê¢ââ¬ê¢ââ¬ pickup_address (endereêÂ§o de coleta)
ê¢âÅê¢ââ¬ê¢ââ¬ delivery_address (endereêÂ§o de entrega)
ê¢âÅê¢ââ¬ê¢ââ¬ status (PENDING_PAYMENT ê¢â â DELIVERED)
ê¢âÅê¢ââ¬ê¢ââ¬ Payment (pagamento via Pix)
ê¢ââê¢ââ¬ê¢ââ¬ Rating (avaliaêÂ§êÂ£o pêÂ³s-entrega)

Address (endereêÂ§os salvos do cliente)
```

---

## Modelo de NegêÂ³cio

### Comissionamento

| Tipo de Entrega | ComissêÂ£o Plataforma | Ganho Entregador |
|-----------------|---------------------|------------------|
| Standard | 20% | 80% |
| Express | 20% | 80% |

### PrecificaêÂ§êÂ£o Base

- **Tarifa base**: R$ 5,00
- **Por km**: R$ 2,00
- **Multiplicador Express**: 1.5x
- **Taxa mêÂ­nima**: R$ 8,00

---

## DocumentaêÂ§êÂ£o TêÂ©cnica

| Documento | LocalizaêÂ§êÂ£o |
|-----------|-------------|
| PRD (Requisitos) | `docs/prd.md` |
| Arquitetura | `docs/architecture.md` |
| Coding Standards | `docs/architecture/coding-standards.md` |
| Tech Stack | `docs/architecture/tech-stack.md` |
| Stories (êâ°picos) | `docs/prd/epic-*.md` |
| Stories (Detalhadas) | `docs/stories/story-*.md` |

---

## Roadmap

### Fase 1: MVP (Backend Completo ê¢Åâ¦)
- [x] Infraestrutura base (monorepo, DB, auth)
- [x] API Cliente (perfil, endereêÂ§os, pedidos, pagamento, tracking)
- [x] API Entregador (cadastro, aceite, coleta, entrega, ganhos)
- [x] API Admin (dashboard, usuêÂ¡rios, pedidos, financeiro)
- [ ] Frontend Mobile (React Native)
- [ ] Frontend Web Admin (Next.js)

### Fase 2: ExpansêÂ£o
- [ ] MêÂ³dulo de transportadoras (Epic 5 - stories prontas)
- [ ] IntegraêÂ§êÂ£o Mercado Pago (Pix real)
- [ ] Push notifications (Firebase)
- [ ] App iOS/Android nas lojas

### Fase 3: Escala
- [ ] ExpansêÂ£o para outros nichos (congelados)
- [ ] API aberta para integraêÂ§êÂµes
- [ ] Programa de fidelidade

---

## ContribuiêÂ§êÂ£o

Este êÂ© um projeto privado. Para contribuir:

1. FaêÂ§a um fork do repositêÂ³rio
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanêÂ§as (`git commit -m 'feat: Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

### ConvenêÂ§êÂµes de Commit

Usamos [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` Nova funcionalidade
- `fix:` CorreêÂ§êÂ£o de bug
- `docs:` DocumentaêÂ§êÂ£o
- `refactor:` RefatoraêÂ§êÂ£o
- `test:` Testes
- `chore:` ManutenêÂ§êÂ£o

---

## LicenêÂ§a

Projeto privado - Todos os direitos reservados.

---

## Contato

Para mais informaêÂ§êÂµes sobre o projeto, entre em contato com a equipe de desenvolvimento.

---

Projeto  - ARCKHÉe