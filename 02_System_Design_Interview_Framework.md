# 02. System Design Interview Framework

---

## Why Do You Need a Framework?

A structured framework helps you approach any system design question methodically. It ensures you cover all critical aspects, communicate clearly, and avoid missing important requirements during interviews.

---

## The 7-Step System Design Interview Framework

### 1. Clarify Requirements

- Ask for functional requirements (core features, nice-to-haves).
- Ask about non-functional requirements (scale, latency, consistency, availability, security).
- Identify who the users are and what their goals are.
- Examples:
    - Should the system support image uploads?
    - What’s the expected latency for a user action?

### 2. Estimate Scale and Constraints

- Number of users, requests per second, data size, growth rate.
- Storage, throughput, and performance targets.
- Example:
    - “Suppose we have 100M users, with 10M daily active users and 1,000 writes/sec at peak.”

### 3. High-Level Architecture

- Draw a block diagram: clients, API gateways, microservices, databases, caches, load balancers, external integrations.
- Show basic data flow (request → process → response).
- Example:
    - User → Load Balancer → Web Servers → App Servers → Database.

### 4. Deep Dive into Key Components

- Data modeling: tables, sharding, indexing.
- Caching: what, where, and how to cache.
- Asynchronous processing: job queues, pub/sub.
- APIs: endpoints, rate limiting, authentication.
- Storage: object stores, CDN, backups.
- Focus on bottlenecks and core challenges.

### 5. Identify and Address Bottlenecks

- Single points of failure (SPOF), scalability limits.
- Discuss how to partition, replicate, or scale components.
- Load balancing, failover, redundancy.

### 6. Address Reliability, Availability, Security

- Data backups, replication, disaster recovery.
- Monitoring and alerting.
- Authentication and authorization.
- Rate limiting, DDoS protection.

### 7. Summarize & Trade-offs

- Recap your design and justify choices.
- Discuss alternatives and why you did/didn’t choose them.
- Address open questions and next steps.
- Example:
    - “We chose eventual consistency for availability; strong consistency would reduce throughput.”

---

## Template for System Design Interview

```
1. Clarify requirements and ask questions.
2. Estimate scale and constraints.
3. Draw high-level architecture.
4. Deep dive into core components (data model, APIs, caching, etc.).
5. Discuss scalability, reliability, and bottlenecks.
6. Address security, monitoring, and operational concerns.
7. Summarize design, discuss trade-offs and next steps.
```

---

## Example: URL Shortener Interview Walkthrough

1. **Clarify Requirements:** Custom short codes? Link expiration? Analytics?
2. **Estimate Scale:** 500M URLs, 1B clicks per day.
3. **Architecture Diagram:** Load balancer → API servers → DB (sharded) → Cache.
4. **Deep Dive:** How to ensure unique short codes? How to scale lookups?
5. **Bottlenecks:** Database writes, link resolution, analytics aggregation.
6. **Security:** Rate limiting, abuse prevention, monitoring.
7. **Summary:** Alternatives (NoSQL, in-memory cache), trade-offs (latency vs. consistency).

---

## Communication Tips

- Narrate your thinking.
- Use diagrams and write key points.
- Pause to check for interviewer feedback.
- Prioritize critical paths.

---

## Common Pitfalls

- Not asking clarifying questions.
- Skipping scale estimation.
- Getting stuck in implementation details.
- Ignoring trade-offs or edge cases.

---

## Practice Exercise

- Pick a sample question (e.g., "Design a photo-sharing service") and walk through these 7 steps aloud or with a peer.

---

## Further Reading

- [System Design Primer](https://github.com/donnemartin/system-design-primer)
- [Grokking the System Design Interview](https://www.designgurus.io/course/system-design-interview)
- [Designing Data-Intensive Applications](https://dataintensive.net/)

---
