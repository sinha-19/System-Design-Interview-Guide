# 12. Monitoring, Logging & Alerting

---

## Why Monitoring & Logging Matter

Monitoring and logging are crucial for maintaining the health, performance, and security of software systems. They enable rapid detection, diagnosis, and resolution of issues, and provide valuable insights for optimization and compliance.

---

## Key Concepts

- **Monitoring:** Collecting metrics and health data from your system.
- **Logging:** Recording events, errors, and important information for auditing and debugging.
- **Alerting:** Notifying operators of abnormal or critical conditions.

---

## What to Monitor

- System metrics: CPU, memory, disk, network.
- Application metrics: request rate, error rate, latency, throughput.
- Business metrics: signups, purchases, conversions.
- Infrastructure metrics: database connections, queue depths, cache hit rates.

---

## Types of Logs

- **Application logs:** App-level events, errors, warnings, info.
- **Access logs:** HTTP requests, status codes, response times.
- **Audit logs:** Security, user actions, compliance.
- **System logs:** OS/kernel events, resource usage.

---

## Log Management

- Use structured logging (JSON, key-value) for easy parsing.
- Centralize logs using log aggregators (ELK Stack, Graylog, Splunk).
- Tag logs with metadata (request ID, user ID, correlation ID).
- Rotate and retain logs per policy (GDPR, HIPAA).

---

## Metrics

- **Gauge:** Current value (e.g., memory usage).
- **Counter:** Monotonically increasing (e.g., number of requests).
- **Histogram:** Distribution (e.g., request latency buckets).
- **Summary:** Percentiles, averages.

---

## Alerting

- Set thresholds for metrics (e.g., error rate > 1%).
- Use alerting platforms (PagerDuty, Opsgenie, VictorOps).
- Define runbooks for on-call engineers.
- Avoid alert fatigue—tune thresholds and suppress flapping.

---

## Distributed Tracing

- Tracks requests across services (Jaeger, Zipkin, OpenTelemetry).
- Correlate logs and metrics using trace IDs.

---

## Dashboards

- Real-time and historical views of system health.
- Tools: Grafana, Kibana, Datadog, CloudWatch.

---

## Best Practices

- Monitor all critical paths (API endpoints, DB queries, background jobs).
- Log at appropriate levels (info, warning, error, critical).
- Secure logs (encryption, access control).
- Regularly review and update alerts.
- Test monitoring and alerting setups before production.

---

## Common Patterns

- **Health Checks:** Endpoints that report service health.
- **Heartbeats:** Regular “I am alive” signals from components.
- **Synthetic Monitoring:** Automated tests simulating user flows.

---

## Compliance

- Audit logs for sensitive actions.
- Retention and access policies for regulatory requirements.

---

## Interview Questions

- How do you detect and diagnose a memory leak?
- What is structured logging and why is it useful?
- How would you set up monitoring for a microservices system?
- What is distributed tracing and when is it needed?

---

## Exercises

- Configure Prometheus and Grafana to monitor a web application.
- Set up log forwarding from application servers to ELK.
- Implement a health check endpoint for your service.
- Create an alert for high error rates.

---

## References

- [Prometheus Monitoring](https://prometheus.io/)
- [Grafana Dashboards](https://grafana.com/)
- [ELK Stack Guide](https://www.elastic.co/what-is/elk-stack)
- [OpenTelemetry](https://opentelemetry.io/)

---

## Summary

Monitoring, logging, and alerting are the backbone of system reliability and observability. Mastering these tools and practices is essential for building and operating resilient systems.

---
