# 16. Case Studies: Common Interview Questions

---

## Approach

For each case, follow the system design interview framework: clarify requirements, estimate scale, draw high-level architecture, deep dive into critical components, discuss trade-offs, and summarize.

---

## 1. Design a URL Shortener (e.g., bit.ly)

- **Requirements:** Shorten URLs, redirect, track analytics, custom aliases.
- **Scale:** Billions of URLs, high read/write.
- **Architecture:**
    - API servers, load balancer, database (sharded), cache for hot links.
    - Unique code generator, hash collision handling.
- **Challenges:** Uniqueness, high write throughput, cache invalidation, analytics aggregation.
- **Trade-offs:** Strong consistency for write, eventual for analytics.

---

## 2. Design Twitter News Feed

- **Requirements:** User timeline, follows/followers, likes, retweets.
- **Scale:** Millions of users, millions of posts/day.
- **Architecture:**
    - Write fan-out (push updates at tweet time) vs. read fan-out (fetch at read time).
    - Timeline service, caching, search index, sharded storage.
- **Challenges:** Latency, feed freshness, storage.
- **Trade-offs:** Storage cost vs. read speed.

---

## 3. Design a Chat System (e.g., WhatsApp)

- **Requirements:** Real-time messaging, group chats, delivery receipts, media sharing.
- **Scale:** Billions of messages/day.
- **Architecture:**
    - Persistent connections (WebSockets), message queues, sharded storage.
    - Delivery acknowledgments, distributed presence system.
- **Challenges:** Message ordering, offline delivery, scaling groups.
- **Trade-offs:** Consistency vs. availability for message delivery.

---

## 4. Design a File Storage Service (e.g., Dropbox)

- **Requirements:** Upload/download, versioning, sharing, sync across devices.
- **Scale:** Petabytes of files, millions of users.
- **Architecture:**
    - Object storage (S3), metadata DB, chunking large files, CDN for downloads.
    - Background sync and conflict resolution.
- **Challenges:** Consistency, deduplication, sync conflicts.
- **Trade-offs:** Latency vs. durability.

---

## 5. Design a Ride-Sharing System (e.g., Uber)

- **Requirements:** Matching riders/drivers, real-time tracking, pricing, trip history.
- **Scale:** Millions of rides/day.
- **Architecture:**
    - Geo-indexing, real-time pub/sub, driver/rider matching service.
    - Payment service, trip history DB.
- **Challenges:** Low latency for matching, surge pricing, fraud detection.
- **Trade-offs:** Accuracy vs. speed for ETA calculation.

---

## 6. Design a Notification System

- **Requirements:** Send email, SMS, push notifications; retry, deduplication.
- **Scale:** Millions of notifications/hour.
- **Architecture:**
    - Message queue, worker pool, external service adapters.
    - Retry logic, DLQ for failures.
- **Challenges:** Rate limiting, deliverability, monitoring.
- **Trade-offs:** Speed vs. reliability.

---

## 7. Design a Rate Limiter

- **Requirements:** Per-user/IP limits, distributed enforcement, real-time metrics.
- **Scale:** Billions of requests/day.
- **Architecture:**
    - Distributed cache (Redis), token bucket/leaky bucket algorithm.
    - API gateway integration.
- **Challenges:** Consistency across regions, burst handling.
- **Trade-offs:** Strictness vs. availability.

---

## Practice Tips

- Always clarify requirements.
- Use diagrams and pseudocode for clarity.
- Discuss bottlenecks and mitigation strategies.
- Summarize and revisit trade-offs at the end.

---

## Exercises

- Pick any case and present a 10-minute system design walkthrough to a peer.
- Draw the architecture for a collaborative document editor.
- Optimize the design for a mobile-first audience.

---

## References

- [System Design Primer](https://github.com/donnemartin/system-design-primer)
- [Grokking the System Design Interview](https://www.designgurus.io/course/system-design-interview)
- [Designing Data-Intensive Applications](https://dataintensive.net/)

---

## Summary

Practice with common system design questions builds the skills and confidence needed for interviews and real-world architecture challenges.

---
