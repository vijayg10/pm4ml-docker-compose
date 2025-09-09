# Payment Manager - Docker Compose Stack

This repository provides a **Docker Compose stack** for running the **Payment Manager** in a **lightweight, single-machine production setup**.  
It is designed for **DFSPs (Digital Financial Service Providers)** who need a simplified deployment alternative to Kubernetes-based infrastructure.

## Features
- PM4ML Core Services
- Keycloak
- API Gateway
- Vault
- Other core dependencies bundled together

## Usage
```bash
git clone https://github.com/your-org/pm4ml-docker-compose.git
cd pm4ml-docker-compose
docker compose up -d