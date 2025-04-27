# Full-Stack Node + TS + React Template

[![Build Status](https://img.shields.io/github/workflow/status/wingtonbrito/full-stack-node-ts-react-template/CI)](link-to-your-ci)
[![License](https://img.shields.io/github/license/wingtonbrito/full-stack-node-ts-react-template)](LICENSE)

**Production-grade** starter for modern web apps, featuring:

- ✅ **Tech Stack:** Node.js · TypeScript · Express · React · TypeORM · PostgreSQL
- ✅ **Infrastructure:** Docker · Terraform · AWS (EC2, Lambda, API Gateway)  
- ✅ **CI/CD:** GitHub Actions pipelines for lint/test/build/deploy  
- ✅ **Architectural Patterns:** Modular microservices, REST + WebSocket APIs  
- ✅ **Monitoring & Metrics:** (add badges if you integrate e.g. Datadog/New Relic)

---

### Description:

### Backend

- POST route that starts a new application
- GET route that can retrieve the current application
- PUT route that will update the application with provided data
- POST route that validates the application and returns a number

### Frontend
- React application that can display the current application state

## 🚀 Quick Start

1. **Clone & Install**  
   ```bash
   git clone git@github.com:wingtonbrito/full-stack-node-ts-react-template.git
   cd full-stack-node-ts-react-template
   npm install```


# full-stack-node-ts-react-template

[![Build Status](https://img.shields.io/github/actions/workflow/status/wingtonrbrito/full-stack-node-ts-react-template/ci.yml?branch=main&style=flat-square)](https://github.com/wingtonrbrito/full-stack-node-ts-react-template/actions)  
[![License](https://img.shields.io/github/license/wingtonrbrito/full-stack-node-ts-react-template?style=flat-square)](LICENSE)

**Production-grade** starter for modern web apps, powered by:

- **Backend:**  
  - **Framework**: Ts.ED (Express) + TypeScript  
  - **ORM**: TypeORM + PostgreSQL  
  - **Validation & Docs**: AJV + Swagger  
- **Frontend:**  
  - **Library**: React (Create-React-App) + TypeScript  
  - **Styling**: your choice (e.g. CSS modules / styled-components)  
- **Infrastructure:**  
  - **Containers**: Docker & Docker-Compose  
  - **Orchestration**: Terraform (optional)  
  - **Cloud**: AWS (EC2, Lambda, API Gateway)  
- **CI/CD:** GitHub Actions (lint, test, build, deploy)  
- **Patterns:** Modular microservices • REST + WebSocket  
- **Monitoring:** Hook in Datadog / New Relic badges here  

---

## 🚀 Quick Start

### 1. Clone & Install

```bash
git clone git@github.com:wingtonrbrito/full-stack-node-ts-react-template.git
cd full-stack-node-ts-react-template
npm install
```

### 2. Bring up the stack

```bash
docker-compose up -d
```

This will launch:
- **Postgres** (`5432`)  
- **PgAdmin** (`5050`)  
- **API server** (`8083`)  

### 3. Browse & Test

- **API Docs (Swagger)** → http://localhost:8083/docs  
- **PgAdmin** → http://localhost:5050 (user: `pgadmin4@pgadmin.org`, pass: `admin`)  
- **React App** → http://localhost:3000  

---

## 📦 What’s Inside

### 🔧 Backend (`/src`)

- **controllers/** – Ts.ED REST endpoints  
- **models/** – TypeORM entities  
- **services/** – Business logic & data access  
- **config/** – Environment, DB & Swagger setup  

#### Key Routes

| Method | Path                                | Description                                 |
|:------:|:------------------------------------|:--------------------------------------------|
| POST   | `/v1/insurance_endpoint`            | Create a new application                    |
| GET    | `/v1/insurance_endpoint/:id`        | Retrieve an existing application by ID      |
| PUT    | `/v1/insurance_endpoint/:id`        | Update an existing application              |
| POST   | `/v1/insurance_endpoint/:id/validate` | Validate and calculate score               |

### 💻 Frontend (`/client`)

- Built with Create-React-App & TypeScript  
- Displays & edits “application” state via your API  

---

## 🐳 Docker & Docker-Compose

**`docker-compose.yml`** spins up:

```yaml
version: '3.5'
services:
  postgres:
    image: postgres:11
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: changeme
      POSTGRES_DATABASE: postgres

  pgadmin:
    image: dpage/pgadmin4
    ports:
      - "5050:80"
    environment:
      PGADMIN_DEFAULT_EMAIL: pgadmin4@pgadmin.org
      PGADMIN_DEFAULT_PASSWORD: admin

  server:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8083:8083"
    depends_on:
      - postgres
```

---

## ✅ Scripts & Commands

- **Build & compile**  
  ```bash
  yarn build        # barrelsby + tsc
  ```
- **Dev server (hot-reload)**  
  ```bash
  yarn start        # ts-node-dev watch
  ```
- **Prod start**  
  ```bash
  yarn start:prod   # node dist/index.js
  ```
- **Lint & format**  
  ```bash
  yarn test:lint
  yarn test:lint:fix
  yarn prettier
  ```
- **Test suite**  
  ```bash
  yarn test         # jest
  ```

---

## 📖 Learn More

- **Ts.ED** → https://tsed.io  
- **TypeORM** → https://typeorm.io  
- **Create-React-App** → https://create-react-app.dev  
- **Docker-Compose** → https://docs.docker.com/compose/

---

> _This template is MIT-licensed—feel free to adapt & extend!_