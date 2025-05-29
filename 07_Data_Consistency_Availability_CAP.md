# 07. Data Consistency, Availability & CAP Theorem

---

## Data Consistency

**Data consistency** ensures all users see the same data at the same time. It’s crucial for transactions, user experience, and correctness.

---

## Types of Consistency

- **Strong Consistency:** After a write, all subsequent reads return the latest value.
- **Weak Consistency:** Reads may return stale data.
- **Eventual Consistency:** All updates propagate, but reads can be stale for a while.
- **Read-Your-Writes:** A user sees their own writes immediately.
- **Causal Consistency:** Operations that are causally related are seen by all in the same order.

---

## Availability

**Availability** measures whether a system is operational and accessible when required. High availability (HA) means minimal downtime and fast failure recovery.

---

## Partition Tolerance

**Partition tolerance** is the ability of a system to continue operating even if network failures split it into isolated sub-networks (partitions).

---

## The CAP Theorem

In a distributed system, you can only guarantee two of the following three:

- **Consistency (C):** Every read gets the latest write or an error.
- **Availability (A):** Every request receives a non-error response, without guarantee it contains the latest write.
- **Partition Tolerance (P):** The system continues to operate despite any network partition.

---

## CAP Scenarios

- **CA (No Partition Tolerance):** RDBMS on a single machine.
- **CP (No Availability):** MongoDB (default), HBase.
- **AP (No Consistency):** DynamoDB, Cassandra.

---

## PACELC Theorem

- Extends CAP: If Partition (P), choose between Availability (A) and Consistency (C); Else (E), choose between Latency (L) and Consistency (C).
- Real-world systems must balance all these factors.

---

## Designing for Consistency

- **Quorum-based Writes/Reads:** Majority of nodes must respond.
- **Leader-based Replication:** Only leader handles writes.
- **Vector Clocks & Versioning:** Track causality, resolve conflicts.

---

## Designing for Availability

- **Replication:** Multiple nodes can serve data.
- **Load Balancing:** Distribute load, avoid hotspots.
- **Failover:** Automatic switching to backup nodes.

---

## Consistency Patterns

- **Read-after-Write Consistency:** Guarantees your writes are visible to you.
- **Monotonic Reads:** Once you’ve seen a value, you never see an older value.
- **Monotonic Writes:** Writes by a client are seen in order.

---

## Real-World Examples

- **Banking:** Needs strong consistency.
- **Social Media Feeds:** Can use eventual consistency.
- **E-commerce Inventory:** Depends on business needs—often strong consistency.

---

## Trade-offs

- **High consistency** can increase latency or reduce availability.
- **High availability** can risk serving stale data.

---

## Interview Questions

- What is the CAP theorem? Give an example.
- How would you design a system for both high availability and strong consistency?
- What consistency model would you use for a chat app?
- How do distributed databases handle network partitions?

---

## Exercises

- Sketch a system that prioritizes availability over consistency and explain your reasoning.
- Analyze the consistency model of DynamoDB or Cassandra.
- Simulate a partition and describe how your system behaves.

---

## References

- [CAP Theorem (Wikipedia)](https://en.wikipedia.org/wiki/CAP_theorem)
- [PACELC Explained](https://en.wikipedia.org/wiki/PACELC_theorem)
- [Designing Data-Intensive Applications](https://dataintensive.net/)

---

## Summary

Consistency, availability, and partition tolerance are foundational for distributed systems. The right balance depends on your system’s goals and expected failures.

---
