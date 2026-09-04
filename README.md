# ESHOP-MICROSERVICES

A .NET microservices project built by following an online tutorial course, step by step, as a way to learn microservices architecture and its surrounding patterns hands-on.

## What I learned

- **Microservices architecture** — independent services (Catalog, Basket, Discount, Ordering), each with its own database
- **API Gateway** — YARP reverse proxy routing client requests to the right service
- **Vertical Slice Architecture** — organizing code by feature instead of by technical layer
- **DDD (Domain-Driven Design)** — used in the Ordering service (Domain / Application / Infrastructure / API layers)
- **CQRS + MediatR** — separating commands and queries, decoupling handlers from controllers
- **gRPC** — used by the Discount service for fast internal service-to-service communication
- **Async communication** — RabbitMQ + MassTransit for messaging between services
- **Containerization** — Docker Compose to run all services, databases (PostgreSQL, SQL Server), Redis, and RabbitMQ together

## Services

| Service | Purpose |
|---|---|
| `Catalog.API` | Product catalog |
| `Basket.Api` | Shopping basket (Redis-backed) |
| `Discount.Grpc` | Discount lookup via gRPC |
| `Ordering.API` | Order management (DDD + CQRS) |
| `YarpApiGateway` | Single entry point routing to all services |
| `Shopping.Web` | Web client |

## Running it

```
cd src
docker-compose up
```

## Note

This is a learning project, not production code — built to understand the concepts, not to ship.
