# 09. Microservices & API Design

---

## What are Microservices?

Microservices architecture breaks a system into small, independent services, each responsible for a specific business capability. Services communicate over APIs, typically via HTTP/gRPC.

---

## Monolith vs. Microservices

- **Monolith:** All logic in a single codebase; simple, but can be hard to scale and maintain.
- **Microservices:** Each service is independent; scales and evolves separately, but introduces complexity.

---

## Benefits of Microservices

- Independent deployment and scaling.
- Technology and language flexibility.
- Fault isolation—failure in one service doesn't bring down the whole system.
- Aligns teams with business domains (Conway’s Law).

---

## Challenges

- Network latency and failure.
- Data consistency across services.
- Increased operational overhead (deployments, monitoring, security).
- Complex testing and debugging.

---

## API Design Principles

- **Consistency:** Uniform resource naming, HTTP methods.
- **Versioning:** `/api/v1/` style URIs.
- **Documentation:** Swagger/OpenAPI for clarity and onboarding.
- **Security:** Authentication (OAuth2, JWT), authorization, rate limiting.
- **Error Handling:** Use standard HTTP status codes and structured error responses.
- **Idempotency:** Ensure safe retries for POST/PUT requests.

---

## REST vs. gRPC

- **REST:** Human-readable, uses HTTP, flexible but less performant for high-throughput.
- **gRPC:** Binary protocol, faster, supports streaming, strong contracts (protobuf).

---

## Service Discovery

- Registry of available services (Consul, Eureka).
- Enables dynamic scaling and failover.

---

## Inter-Service Communication

- **Synchronous:** HTTP/gRPC.
- **Asynchronous:** Messaging/queueing (Kafka, RabbitMQ).
- **API Gateway:** Central entry point for routing, authentication, rate limiting.

---

## Data Management

- **Database per service:** Avoids tight coupling.
- **Eventual consistency:** Use events to sync data across services.
- **Saga pattern:** Manages distributed transactions.

---

## Testing Microservices

- Unit, integration, and contract testing.
- Test with stubs/mocks for dependencies.

---

## Deployment

- Use containers (Docker, Kubernetes).
- CI/CD pipelines for independent services.
- Blue/green and canary deployments for safe rollouts.

---

## Monitoring

- Distributed tracing (Jaeger, Zipkin).
- Aggregated logging and metrics.

---

## Interview Questions

- What are the pros and cons of microservices?
- How do you manage data consistency across services?
- How would you design a versioned REST API?
- What is an API gateway and why is it used?

---

## Exercises

- Design a simple microservices system (user, order, payment).
- Implement a REST API with versioning and error handling.
- Set up service discovery and health checks in Docker Compose.

---

## References

- [Microservices.io](https://microservices.io/)
- [Building Microservices by Sam Newman](https://samnewman.io/books/building_microservices/)
- [OpenAPI Specification](https://swagger.io/specification/)

---

## Summary

Microservices and robust API design enable modular, scalable architectures. Understanding the patterns and trade-offs is key for modern system design and interviews.

---
