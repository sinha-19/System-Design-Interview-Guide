# 05. Caching Strategies

---

## What is Caching?

Caching is the technique of storing frequently accessed data in a fast, temporary storage layer to reduce latency and backend load. Caching is critical for high-performance and scalable system architectures.

---

## Why Use Caching?

- **Reduces latency:** Serves data quickly from memory or edge.
- **Minimizes backend load:** Fewer database or API calls.
- **Improves user experience:** Faster page loads and responses.
- **Supports high throughput:** Handles spikes in traffic.

---

## Types of Caches

### 1. Client-Side Cache

- Browser or device stores responses.
- Reduces repeated requests to the server.
- Example: HTTP cache headers, Service Workers.

### 2. CDN (Content Delivery Network) Cache

- Edge servers cache static content (images, JS, CSS) globally.
- Example: Cloudflare, Akamai, AWS CloudFront.

### 3. Reverse Proxy Cache

- Caches responses at the gateway (NGINX, Varnish).
- Reduces load on application servers.

### 4. In-Memory Cache

- Fastest, used for hot data (Redis, Memcached).
- Can be used for session storage, leaderboards, etc.

### 5. Application-Level Cache

- Cache objects or query results in application memory (singleton, per-request, etc.).

---

## Cache Placement

- **Database query cache:** Caches expensive query results.
- **Web/app server cache:** Stores rendered pages or fragments.
- **API response cache:** Reduces repeated computations or third-party calls.

---

## Cache Invalidation

- **Time-based (TTL):** Data expires after a set time.
- **Write-through:** Update cache and database together.
- **Write-back (write-behind):** Update cache, then persist to database.
- **Explicit/Manual:** Invalidate or update cache when data changes.
- **Event-based:** Listen for updates and update cache accordingly.

---

## Consistency Models

- **Strong Consistency:** Cache is always in sync with source.
- **Eventual Consistency:** Cache may lag behind source briefly.
- **Read-Through:** Cache fetches from DB on miss.
- **Write-Through:** Writes go to cache and DB simultaneously.

---

## Cache Eviction Policies

- **LRU (Least Recently Used):** Evicts items not used recently.
- **LFU (Least Frequently Used):** Evicts items used least often.
- **FIFO (First-In-First-Out):** Removes oldest items.
- **Random:** Removes random items (rarely used).

---

## Cache Stampede & Mitigation

- Stampede: Multiple requests miss cache and hit DB at once.
- Mitigation: Use request coalescing, locks, or stale-while-revalidate.

---

## Cache Warming

- Pre-populate cache with anticipated hot data after startup or deployment.

---

## Caching Pitfalls

- **Stale Data:** Clients see outdated information.
- **Inconsistency:** Data in cache and DB diverge.
- **Over-caching:** Caching everything can lead to memory issues.
- **Under-caching:** Not leveraging cache enough increases latency.

---

## Security Considerations

- Do not cache sensitive or user-specific data in shared caches.
- Use HTTPS to prevent cache poisoning.

---

## Example Use Case: Caching User Profiles

- Store user profiles in Redis.
- On cache miss, fetch from DB and update cache.
- Invalidate cache on profile update.

---

## Interview Questions

- How do you ensure cache consistency?
- What is a cache stampede? How would you prevent it?
- When should you use a CDN vs. an in-memory cache?
- How do you choose an eviction policy?

---

## Exercises

- Implement Redis caching for a REST API.
- Simulate a cache stampede and resolve it.
- Tune cache TTLs and observe performance trade-offs.

---

## References

- [Redis Documentation](https://redis.io/documentation)
- [NGINX Caching Guide](https://docs.nginx.com/nginx/admin-guide/content-cache/content-caching/)
- [AWS Caching Best Practices](https://aws.amazon.com/caching/)

---

## Summary

Caching is a powerful tool for boosting system performance and scalability. Mastering caching strategies and trade-offs is vital for system design interviews and real-world projects.

---
