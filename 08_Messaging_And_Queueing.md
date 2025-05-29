# 08. Messaging & Queueing Systems

---

## What is Messaging & Queueing?

Messaging and queueing decouple components, allowing them to communicate asynchronously. This improves scalability, reliability, and resilience to spikes or failures.

---

## Why Use Queues?

- **Decoupling:** Producers and consumers operate independently.
- **Buffering:** Absorb load spikes.
- **Asynchronous Processing:** Offload time-consuming tasks.
- **Retry Logic:** Handle transient failures gracefully.
- **Load Leveling:** Smooth out variable workloads.

---

## Types of Messaging Systems

### 1. Message Queues

- FIFO ordering, reliable delivery.
- Example: RabbitMQ, AWS SQS, ActiveMQ.

### 2. Publish-Subscribe (Pub/Sub)

- Producers publish messages to a topic; consumers subscribe to topics.
- Enables fan-out to multiple consumers.
- Example: Kafka, Google Pub/Sub.

### 3. Event Streams

- High-throughput, append-only logs.
- Replayable, persistent.
- Example: Kafka, Kinesis.

---

## Key Concepts

- **Producer:** Sends messages.
- **Consumer:** Receives/processes messages.
- **Broker:** Mediates between them (the queue or topic).
- **Topic:** Channel for pub/sub.
- **Ack/Nack:** Acknowledge or reject a message.

---

## Delivery Guarantees

- **At Most Once:** No duplicates, but may lose messages.
- **At Least Once:** No loss, but may see duplicates.
- **Exactly Once:** No loss, no duplicates (complex and rare).

---

## Message Ordering

- Guaranteed ordering (FIFO) may reduce throughput.
- Partitioned topics allow parallelism but only per partition.

---

## Durability

- Persistent queues write messages to disk.
- In-memory queues are faster but may lose messages on crash.

---

## Scaling Messaging Systems

- Partition queues/topics for parallelism.
- Add brokers for higher throughput.
- Use consumer groups to scale processing.

---

## Dead Letter Queues (DLQ)

- Capture messages that fail to be processed after retries.
- Useful for debugging and alerting.

---

## Monitoring & Metrics

- Queue length, processing lag, failed messages.
- Consumer throughput, broker health.

---

## Common Use Cases

- Email/SMS notification systems.
- Order processing and billing.
- Log aggregation and real-time analytics.
- Task scheduling and background jobs.

---

## Interview Questions

- How do you design a reliable notification system?
- What’s the difference between at-least-once and exactly-once delivery?
- How would you handle message deduplication?
- When would you use pub/sub over point-to-point queues?

---

## Exercises

- Set up a RabbitMQ or Kafka instance and send/consume messages.
- Implement retry and backoff logic for failed messages.
- Design a DLQ and monitoring dashboard for a queue.

---

## References

- [RabbitMQ Official Docs](https://www.rabbitmq.com/documentation.html)
- [Kafka Documentation](https://kafka.apache.org/documentation/)
- [AWS SQS](https://aws.amazon.com/sqs/)

---

## Summary

Messaging and queueing systems provide the backbone for scalable, resilient, and decoupled architectures. Mastering them is crucial for building modern, distributed systems.

---
