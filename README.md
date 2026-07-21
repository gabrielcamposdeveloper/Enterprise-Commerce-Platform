# Enterprise Commerce Platform - Version 1

Uma plataforma open source de e-commerce desenvolvida com foco em arquitetura moderna, escalabilidade e boas práticas de desenvolvimento. O objetivo do projeto é servir como referência para desenvolvedores que desejam aprender ou implementar uma solução baseada em microsserviços utilizando .NET, Angular e tecnologias cloud.

## Objetivo

Criar uma plataforma enterprise que simule um ambiente de produção real, utilizando arquitetura distribuída, comunicação assíncrona, observabilidade, autenticação centralizada e pipelines de integração contínua.

---

# Stack Tecnológica

### Backend

* .NET 9
* ASP.NET Core
* Entity Framework Core
* Dapper
* MediatR
* FluentValidation
* Serilog
* OpenTelemetry

### Frontend

* Angular 20
* Angular Material
* Signals
* RxJS

### Banco de Dados

* PostgreSQL

### Mensageria

* Kafka

### Cache

* Redis

### Busca

* Elasticsearch

### Cloud

* Azure
* Azure Functions
* Azure Blob Storage
* Azure Service Bus

### DevOps

* Docker
* Docker Compose
* Kubernetes
* GitHub Actions

### Observabilidade

* Prometheus
* Grafana
* OpenTelemetry
* Jaeger

---

# Arquitetura

```text
                        Angular Admin
                              │
                              ▼
                        API Gateway (YARP)
                              │
      ┌───────────────────────┼────────────────────────┐
      ▼                       ▼                        ▼
 Identity Service      Catalog Service         User Service
      │                       │                        │
      ▼                       ▼                        ▼
 Order Service         Inventory Service      Payment Service
      │                       │                        │
      └──────────────┬────────┴───────────────┬────────┘
                     ▼
                   Kafka
                     │
      ┌──────────────┼───────────────┐
      ▼              ▼               ▼
 Notification   Audit Service   Reporting Service
                     │
                     ▼
              Elasticsearch
```

---

# Estrutura do Repositório

```text
enterprise-commerce-platform/

apps/
├── angular-admin
├── api-gateway

services/
├── identity-service
├── users-service
├── catalog-service
├── inventory-service
├── orders-service
├── payment-service
├── notification-service
├── audit-service
├── reporting-service

shared/
├── building-blocks
├── contracts
├── event-bus
├── shared-kernel

infrastructure/
├── docker
├── kubernetes
├── terraform

docs/
```

---

# Principais Funcionalidades

## Identidade

* Login
* JWT
* Refresh Token
* OAuth2
* Controle de permissões
* Roles

## Catálogo

* Produtos
* Categorias
* Imagens
* Busca
* Estoque

## Pedidos

* Carrinho
* Checkout
* Histórico
* Status do pedido

## Pagamentos

* Simulação de gateway
* Aprovação
* Cancelamento
* Estorno

## Estoque

* Reserva de produtos
* Baixa automática
* Atualização por eventos

## Notificações

* Email
* SMS
* Push Notification

## Auditoria

* Histórico completo
* Rastreamento de alterações
* Consulta por usuário

## Relatórios

* Produtos mais vendidos
* Faturamento
* Pedidos
* Clientes
* Dashboard

---

# Arquitetura e Padrões

* Clean Architecture
* Domain Driven Design (DDD)
* CQRS
* Vertical Slice Architecture
* Repository Pattern
* Unit of Work
* Outbox Pattern
* Saga Pattern
* Event Driven Architecture
* API Gateway
* Retry Pattern
* Circuit Breaker
* Health Checks
* Idempotência
* Rate Limiting

---

# Observabilidade

* Logs estruturados
* Distributed Tracing
* Métricas
* Dashboards no Grafana
* Tracing com Jaeger
* Monitoramento via Prometheus

---

# Testes

* Testes Unitários
* Testes de Integração
* Testes de Contrato
* Testes End-to-End
* Testes de Performance

---

# Roadmap

### Fase 1

* Identity Service
* Catalog Service
* Users Service
* Angular Admin

### Fase 2

* Orders Service
* Inventory Service
* Kafka
* Redis

### Fase 3

* Payment Service
* Notification Service
* Upload de imagens
* Azure Blob Storage

### Fase 4

* Auditoria
* Elasticsearch
* Dashboard

### Fase 5

* Kubernetes
* Terraform
* GitHub Actions
* Observabilidade completa

---

# Objetivos do Projeto

* Demonstrar arquitetura enterprise utilizando .NET e Angular.
* Explorar comunicação síncrona e assíncrona entre microsserviços.
* Implementar boas práticas de observabilidade, segurança e escalabilidade.
* Servir como referência open source para a comunidade.
* Simular um ambiente de produção próximo ao encontrado em grandes empresas.

Este projeto foi idealizado para evoluir continuamente com novas funcionalidades, integrações e contribuições da comunidade, tornando-se uma referência para arquiteturas modernas baseadas em microsserviços e cloud.
