# 11. Rate Limiting & Throttling

---

## What is Rate Limiting?

Rate limiting restricts the number of requests a user or client can make to a system within a defined time period. It protects services from abuse, ensures fair resource allocation, and maintains system stability under heavy load.

---

## Why Rate Limiting is Important

- **Prevents abuse and DoS attacks:** Stops malicious actors or buggy clients from overwhelming your system.
- **Protects backend resources:** Avoids database or API overload.
- **Fair sharing:** Ensures equitable access for all users.
- **Cost control:** Prevents unexpected cloud or bandwidth bills.

---

## Common Use Cases

- API gateways for public APIs
- Login and signup endpoints to prevent brute force
- Third-party integrations and webhook receivers
- Messaging and notification systems

---

## Rate Limiting Algorithms

### 1. Fixed Window

- Counts requests in a fixed time window (e.g., 100 requests per minute).
- Simple but vulnerable to burst traffic at window edges.

### 2. Sliding Window

- Spreads requests over a moving window (e.g., last 60 seconds).
- Reduces burstiness compared to fixed window.

### 3. Token Bucket

- Tokens added at a fixed rate; requests require a token.
- Allows for short bursts up to bucket size, then throttles.

### 4. Leaky Bucket

- Requests enter a bucket and exit at a fixed rate.
- Excess requests are dropped or delayed.

---

## Implementation Strategies

- **In-memory counters:** Fast but not distributed.
- **Distributed cache:** Use Redis or Memcached for multi-server setups.
- **API gateways:** Many cloud gateways (AWS API Gateway, Kong, NGINX) have built-in support.
- **Custom middleware:** Logic in application code.

---

## Identifying Clients

- By IP address
- By user ID or API key
- By OAuth token or session

---

## Rate Limiting Response

- Return HTTP 429 Too Many Requests
- Include `Retry-After` header to indicate when the client can retry

---

## Throttling

- Actively slows down or rejects requests exceeding allowed rate.
- Can be soft (delayed responses) or hard (drop with error).

---

## Burst Handling

- Allow short spikes using token/leaky bucket.
- Smooths out traffic without penalizing well-behaved users.

---

## Monitoring and Logging

- Track rate limit violations, top offending clients.
- Alert on unusual spikes or patterns.

---

## Bypass and Abuse Considerations

- Distributed attacks from many IPs (“low and slow”).
- Trusted clients may need higher limits (whitelisting).
- Protect internal APIs as well as public endpoints.

---

## API Design Patterns

- Communicate limits and usage via response headers:
  - `X-RateLimit-Limit`
  - `X-RateLimit-Remaining`
  - `X-RateLimit-Reset`
- Provide clear documentation for developers.

---

## Example: Token Bucket in Pseudocode

```python
bucket = {
    'tokens': 10,
    'last_refill': time.now()
}

def allow_request(bucket, refill_rate, capacity):
    now = time.now()
    elapsed = now - bucket['last_refill']
    bucket['tokens'] += elapsed * refill_rate
    bucket['tokens'] = min(bucket['tokens'], capacity)
    bucket['last_refill'] = now
    if bucket['tokens'] >= 1:
        bucket['tokens'] -= 1
        return True
    return False
```

---

## Interview Questions

- How would you design a rate limiting middleware for an API?
- What’s the difference between token bucket and leaky bucket?
- How do you handle rate limiting in a multi-region deployment?
- How do you prevent users from bypassing rate limits?

---

## Exercises

- Implement a sliding window rate limiter in your favorite language.
- Use Redis to store counters for distributed rate limiting.
- Simulate burst traffic and tune your limiter’s parameters.

---

## References

- [Rate Limiting Algorithms (Cloudflare)](https://blog.cloudflare.com/counting-things-a-lot-of-different-things/)
- [NGINX Rate Limiting](https://docs.nginx.com/nginx/admin-guide/security-controls/controlling-access-proxied-http/)
- [AWS API Gateway Throttling](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html)

---

## Summary

Rate limiting and throttling are essential for protecting systems from abuse and managing resources. Understanding algorithms, implementation strategies, and edge cases is crucial for robust API and backend design.

---
