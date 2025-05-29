# 03. Scalability Fundamentals

---

## What is Scalability?

Scalability is the ability of a system to handle increased load, data, or users without compromising performance or reliability. In system design, scalability is a core requirement for modern web applications and platforms.

---

## Types of Scalability

### 1. Vertical Scaling (Scaling Up)
- Adding more resources (CPU, RAM, disk) to a single machine.
- Simple to implement, but limited by hardware.
- Example: Moving from a 4-core server to a 64-core server.

### 2. Horizontal Scaling (Scaling Out)
- Adding more machines or nodes to distribute load.
- More complex, but virtually unlimited growth.
- Common in distributed systems and cloud-native architectures.
- Example: Adding more web servers behind a load balancer.

---

## Stateless vs. Stateful Systems

### Stateless Systems
- No session or user data stored on the server.
- Easier to scale horizontally.
- Example: RESTful APIs, load-balanced web servers.

### Stateful Systems
- Store session or user state on the server.
- Requires sticky sessions or shared state (DB, cache).
- Harder to scale and maintain.

---

## Scaling Patterns

- **Load Balancing:** Distributes requests across multiple servers.
- **Caching:** Reduces database or service load.
- **Sharding:** Splits large datasets across multiple databases.
- **Replication:** Copies data for fault-tolerance and read scaling.
- **Queueing:** Smooths out spikes by decoupling producers and consumers.

---

## Identifying Bottlenecks

- **CPU-bound:** Intense computation.
- **Memory-bound:** Large in-memory datasets.
- **I/O-bound:** Disk or network latency.
- **Database-bound:** Slow queries, lack of indexing.
- **Network-bound:** Limited bandwidth or high latency.

---

## Elasticity

- Ability to automatically add or remove resources based on demand.
- Key for cloud-native systems.
- Use of auto-scaling groups, serverless, and managed services.

---

## High Availability (HA)

- Ensure the system is always accessible, even during failures.
- Achieved by redundancy, failover mechanisms, and replication.

---

## Fault Tolerance

- Ability to continue functioning despite failures.
- Use of retries, circuit breakers, graceful degradation.

---

## CAP Theorem (Brief Overview)

- Consistency, Availability, Partition Tolerance—pick any two.
- Critical for distributed system design.

---

## Scalability in Practice

- Design for 10x or 100x scale from the start.
- Use monitoring and metrics to identify scaling needs.
- Start simple, refactor and optimize as scale grows.

---

## Interview Questions

- How would you scale a read-heavy application?
- What are the trade-offs between vertical and horizontal scaling?
- How do you scale a database to billions of records?
- What is statelessness and why is it important for scalability?

---

## Practice Exercise

- Sketch a scalable architecture for a video streaming platform. Identify which components need to scale and how.

---

## References

- [Google SRE Book](https://sre.google/sre-book/table-of-contents/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [Designing Data-Intensive Applications](https://dataintensive.net/)

---

## Summary

Scalability is about anticipating and planning for growth. Mastering its principles will help you build systems that can serve millions while remaining reliable and performant.

---
