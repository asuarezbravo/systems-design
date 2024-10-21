# 4.3. Sharding: Horizontal Partitioning

## Introduction

Sharding, also known as horizontal partitioning, is a database scaling technique that involves splitting a database into smaller, more manageable pieces called shards. Each shard contains a subset of the data, and together, the shards form the complete dataset. Sharding helps distribute the load across multiple servers, improving performance and scalability.

## Types of Sharding

1. **Range-Based Sharding:**
   - In this approach, each shard is responsible for a specific range of data (e.g., by user ID or date).
   - **Advantages:** Simple to implement and understand.
   - **Disadvantages:** Skewed distribution can lead to certain shards becoming hotspots if the data isn’t evenly distributed.

2. **Hash-Based Sharding:**
   - Data is distributed across shards using a hash function that ensures even distribution.
   - **Advantages:** Provides a balanced load across shards.
   - **Disadvantages:** More complex to implement and may require consistent hashing during shard expansion.

3. **Geographical Sharding:**
   - Shards are based on geographic regions, with each shard responsible for a particular region.
   - **Advantages:** Reduces latency by serving users from the closest region.
   - **Disadvantages:** May lead to uneven data distribution if some regions have significantly more users than others.

## Conclusion

Sharding is an effective way to scale databases horizontally. However, choosing the right sharding strategy depends on the data distribution and access patterns, as different methods have trade-offs in terms of complexity and performance.

---

[Next: 4.4. CAP Theorem and Its Implications](./section_4_4.md)
