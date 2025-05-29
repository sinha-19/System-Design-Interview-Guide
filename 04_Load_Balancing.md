# 04. Load Balancing

---

## What is Load Balancing?

Load balancing is the process of distributing incoming network traffic across multiple servers or resources to ensure no single server bears too much load. It improves system reliability, scalability, and performance.

---

## Why Load Balancing is Critical

- **Prevents server overload:** Distributes requests evenly.
- **Enables horizontal scaling:** Easily add or remove servers.
- **Improves availability:** If one server fails, others can handle traffic.
- **Enhances performance:** Clients are routed to healthy, responsive servers.

---

## Types of Load Balancers

### 1. Hardware Load Balancers

- Specialized appliances, high throughput, expensive.
- Example: F5, Citrix NetScaler.

### 2. Software Load Balancers

- Run on commodity hardware or VMs.
- Example: NGINX, HAProxy, Envoy.

### 3. Cloud/Managed Load Balancers

- Provided as a service by cloud vendors.
- Example: AWS Elastic Load Balancer, Google Cloud Load Balancer.

---

## Load Balancing Algorithms

- **Round Robin:** Each request goes to the next server in a list.
- **Least Connections:** Directs traffic to the server with the fewest active connections.
- **IP Hash:** Uses the client’s IP address to decide which server.
- **Weighted Round Robin:** Assigns more requests to powerful servers.
- **Random:** Requests go to random servers.

---

## Layer 4 vs. Layer 7 Load Balancing

- **Layer 4 (Transport):** Works at TCP/UDP level, faster but less flexible.
- **Layer 7 (Application):** Works at HTTP/HTTPS level, can inspect content, more flexible.

---

## Health Checks

- Regularly ping servers to check availability.
- Remove unhealthy servers from rotation.
- Types: TCP, HTTP, HTTPS checks.

---

## SSL Termination

- Load balancer decrypts SSL/TLS traffic, reducing the load on backend servers.
- Can also re-encrypt before forwarding.

---

## Sticky Sessions

- Also called session affinity.
- Ensures requests from the same client go to the same server.
- Useful when session state is stored locally (not recommended for scalable systems).

---

## Global Load Balancing

- Distributes traffic across multiple data centers or regions.
- Uses DNS-based or Anycast routing.
- Improves latency and disaster resilience.

---

## Load Balancer as a Single Point of Failure

- Must run multiple load balancer instances (active-active, active-passive).
- Use DNS or virtual IP failover.

---

## Caching at Load Balancer

- Some load balancers support content caching (Layer 7).
- Reduces backend load for static or infrequently changing content.

---

## Security Considerations

- DDoS protection: Filters malicious traffic.
- Web Application Firewall (WAF) integration.

---

## Example Architecture

```
Clients
   |
[Load Balancer]
   |         \
[App Server 1] [App Server 2] ...
```

---

## Best Practices

- Monitor and log load balancer metrics.
- Regularly test failover and scaling.
- Tune health check intervals and thresholds.
- Use SSL certificates and keep them up to date.

---

## Interview Questions

- How would you design a load balancing layer for a global service?
- What happens if a load balancer fails?
- What are sticky sessions and when should you avoid them?
- How do you monitor load balancer health and performance?

---

## Exercises

- Set up an NGINX or HAProxy load balancer for a local app.
- Simulate server failure and observe traffic distribution.
- Compare Layer 4 and Layer 7 load balancing in a sample project.

---

## References

- [NGINX Load Balancing](https://docs.nginx.com/nginx/admin-guide/load-balancer/http-load-balancer/)
- [AWS Load Balancer Docs](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)
- [HAProxy Documentation](https://www.haproxy.org/)

---

## Summary

Load balancing is a cornerstone of scalable, highly available systems. Understanding its types, algorithms, and best practices is essential for system design interviews and real-world engineering.

---
