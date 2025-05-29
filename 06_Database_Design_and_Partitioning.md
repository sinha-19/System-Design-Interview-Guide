# 06. Database Design & Partitioning

---

## What is Database Design?

Database design is the process of structuring data storage, access, and management to support system requirements. It’s a cornerstone of scalable, reliable system architecture.

---

## Relational vs. NoSQL Databases

- **Relational (SQL):** Structured schemas, ACID transactions, strong consistency (MySQL, PostgreSQL, Oracle).
- **NoSQL:** Flexible schemas, horizontal scaling, eventual consistency options (MongoDB, Cassandra, DynamoDB).
    - **Document:** JSON-like docs (MongoDB)
    - **Key-Value:** Simple, fast lookups (Redis, DynamoDB)
    - **Columnar:** Wide tables (Cassandra, HBase)
    - **Graph:** Nodes and edges for relationships (Neo4j)

---

## Data Modeling

- **Entities:** Real-world objects (users, products).
- **Attributes:** Properties (name, email, price).
- **Relationships:** How entities connect (one-to-many, many-to-many).
- **Normalization:** Remove redundancy, optimize for consistency.
- **Denormalization:** Add redundancy for performance.

---

## Indexing

- **Purpose:** Speed up queries.
- **Types:** Single-field, composite, full-text, geospatial.
- **Trade-off:** More indexes = faster reads, slower writes.

---

## Query Optimization

- Use explain plans to analyze slow queries.
- Add or remove indexes judiciously.
- Avoid N+1 query problems.
- Batch writes and reads where possible.

---

## Partitioning (Sharding)

- **Horizontal Partitioning (Sharding):** Split rows across DBs for scale.
    - **Hash-based:** Use hash of key (user_id % N).
    - **Range-based:** Use value ranges (date, alphabet).
    - **Directory-based:** Mapping service points to shards.
- **Vertical Partitioning:** Split columns into different tables/databases.

---

## Replication

- Maintain multiple copies of data for reliability.
- **Master-Slave (Primary-Replica):** Reads from replicas, writes to master.
- **Multi-Master:** Writes to multiple nodes; complex conflict resolution.

---

## Consistency Models

- **Strong Consistency:** All nodes see the same data at the same time.
- **Eventual Consistency:** Nodes may lag, but converge eventually.
- **Quorum-Based:** Require a majority of nodes to agree before committing changes.

---

## CAP Theorem

- **Consistency, Availability, Partition Tolerance:** Pick two in a distributed system.
- **CP:** MongoDB (by default)
- **AP:** DynamoDB, Cassandra

---

## Database Scaling Strategies

- **Read Replicas:** Offload reads from primary.
- **Sharding:** Horizontal partitioning for scale.
- **Caching:** Hot data in Redis, Memcached.
- **Connection Pooling:** Efficiently manage DB connections.

---

## Handling Large Datasets

- **Archiving:** Move old data to cold storage.
- **Data Retention Policies:** Purge unneeded records.
- **Batch Processing:** Use ETL tools for analytics.

---

## Schema Evolution

- Use migrations for schema changes.
- Prefer backward-compatible changes in production systems.
- Plan for zero-downtime deployments.

---

## Security

- Least privilege for DB users.
- Encryption at rest and in transit.
- Auditing and monitoring of access.

---

## Interview Questions

- How would you shard a database for a social network?
- What are the trade-offs of denormalization?
- When would you use NoSQL over SQL?
- How do you handle schema migrations in production?
- What is the difference between replication and partitioning?

---

## Exercises

- Design a schema for an e-commerce store (users, products, orders, reviews).
- Implement sharding with hash-based partitioning.
- Analyze and optimize a slow SQL query.
- Simulate failover in a master-replica setup.
- Write a migration to add a new column with a default value.

---

## References

- [Designing Data-Intensive Applications](https://dataintensive.net/)
- [SQL vs. NoSQL Overview](https://www.mongodb.com/nosql-explained)
- [PostgreSQL Partitioning Docs](https://www.postgresql.org/docs/current/partitioning.html)
- [MongoDB Sharding Docs](https://docs.mongodb.com/manual/sharding/)

---

## Summary

Database design and partitioning are essential to support scale, reliability, and performance. Good design choices enable systems to grow and adapt to changing requirements and loads.

---
