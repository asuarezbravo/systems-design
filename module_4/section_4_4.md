# 4.4. CAP Theorem and Its Implications

## Introduction

The CAP theorem, also known as Brewer’s theorem, is a fundamental principle in distributed systems design. It states that a distributed system can provide only two out of the following three guarantees:

- **Consistency (C):** Every read receives the most recent write or an error.
- **Availability (A):** Every request receives a response (success or failure), even without a guarantee that it contains the most recent data.
- **Partition Tolerance (P):** The system continues to operate even if communication between nodes is interrupted (network partition).

## Understanding the CAP Theorem

1. **Consistency vs. Availability:**
   - Systems must choose between consistency and availability during network partitions. For example, relational databases often prioritize consistency, while NoSQL databases prioritize availability.

2. **Partition Tolerance:**
   - Partition tolerance is a requirement for any distributed system since network partitions can happen at any time.

## Real-World Implications

- **CA Systems:** Typically single-node systems that favor consistency and availability but lack partition tolerance.
- **CP Systems:** Prioritize consistency and partition tolerance, sacrificing availability (e.g., traditional relational databases in distributed settings).
- **AP Systems:** Prioritize availability and partition tolerance, sacrificing strict consistency (e.g., NoSQL databases like Cassandra).

## Conclusion

The CAP theorem provides a useful framework for understanding the trade-offs in distributed systems. Depending on the use case, you must decide which properties to prioritize: consistency, availability, or partition tolerance.

---

[Next: 4.5. Distributed Transaction Management](./section_4_5.md)
