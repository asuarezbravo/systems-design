# 4.2. Replication Strategies (Master-Slave, Master-Master)

## Introduction

Replication is the process of copying and maintaining database instances across multiple servers to ensure data redundancy and improve read performance. There are different types of replication strategies, including master-slave and master-master replication. In this section, we will explore these strategies in detail and discuss their advantages and disadvantages.

## Master-Slave Replication

- **How it Works:** In master-slave replication, the master database handles all write operations, and changes are propagated to one or more slave databases, which handle read operations.
- **Advantages:**
  - Simple to set up and manage.
  - Reduces the load on the master database by offloading reads to slaves.
- **Disadvantages:**
  - Failover is manual and requires promotion of a slave to master.
  - Data consistency might be delayed during replication lag.

## Master-Master Replication

- **How it Works:** In master-master replication, all nodes can handle both read and write operations, allowing for more flexibility and redundancy.
- **Advantages:**
  - Redundancy: If one master fails, another can take over without a failover process.
  - Better resource utilization as all nodes are active.
- **Disadvantages:**
  - Increased complexity in handling conflicts and maintaining consistency.
  - Potential for data collisions when multiple masters write simultaneously.

## Conclusion

Both replication strategies have their use cases. Master-slave replication is simpler but requires manual failover, while master-master replication offers higher availability at the cost of increased complexity.

---

[Next: 4.3. Sharding: Horizontal Partitioning](./section_4_3.md)
