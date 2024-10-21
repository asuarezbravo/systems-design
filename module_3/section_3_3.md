# 3.3. Load Balancing Fundamentals

## Introduction

As systems scale horizontally, distributing traffic evenly across multiple servers becomes critical to maintaining performance and availability. **Load balancing** is a technique used to distribute incoming requests across multiple servers to ensure that no single server is overwhelmed by too much traffic.

In this section, we’ll explore the fundamentals of load balancing, different load balancing algorithms, and when to use specific strategies.

## What is Load Balancing?

Load balancing ensures that requests are distributed across a pool of servers in a way that maximizes resource utilization, avoids server overloads, and provides redundancy. By distributing the load, load balancers can ensure that even as traffic increases, no single server becomes a bottleneck.

## Types of Load Balancing

### 1. **Layer 4 (Transport Layer) Load Balancing**
- **Definition:** Operates at the transport layer (TCP/UDP) and distributes traffic based on network information such as IP addresses and ports.
- **Advantages:** Fast and efficient because it works without looking at the content of the requests.
- **Disadvantages:** Offers limited flexibility in traffic routing decisions because it doesn't consider application-level data.

### 2. **Layer 7 (Application Layer) Load Balancing**
- **Definition:** Operates at the application layer (HTTP/HTTPS) and distributes traffic based on content, such as URLs, headers, or cookies.
- **Advantages:** Provides more granular control, allowing requests to be routed based on specific application-level criteria.
- **Disadvantages:** Slower than Layer 4 load balancing due to the additional processing involved in examining the content of the requests.

## Load Balancing Algorithms

### 1. **Round Robin**
- **Definition:** Requests are distributed sequentially to each server in the pool, ensuring an even distribution of traffic.
- **Use Case:** Suitable for scenarios where servers have similar performance and capacity.

### 2. **Least Connections**
- **Definition:** Directs traffic to the server with the fewest active connections, ensuring that no single server gets overloaded.
- **Use Case:** Ideal for systems where request processing times can vary significantly between servers.

### 3. **IP Hash**
- **Definition:** Uses the client's IP address to determine which server should handle the request, ensuring that requests from the same client are always routed to the same server.
- **Use Case:** Useful when maintaining session persistence across requests is critical.

## Importance of Load Balancing

- **High Availability:** Load balancers can detect server failures and route traffic to healthy servers, improving fault tolerance.
- **Scalability:** As more servers are added to the system, the load balancer automatically distributes traffic across them, allowing the system to scale horizontally.
- **Optimized Resource Utilization:** Distributing traffic evenly ensures that all servers are used efficiently, preventing overloading and underutilization.

## Conclusion

Load balancing is an essential technique in horizontal scaling, ensuring that traffic is distributed evenly across servers, optimizing performance, and maintaining high availability. By understanding different load balancing algorithms and their use cases, you can select the best strategy for your system’s needs.

---

[Next: 3.4. Autoscaling Techniques](./section_3_4.md)
