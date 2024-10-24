# 9.3. CDN Caching Strategies

## Introduction

Caching is one of the core mechanisms that allow CDNs to accelerate content delivery. By storing frequently requested content on edge servers, CDNs can reduce the number of requests that need to be sent to the origin server, improving performance and reducing latency. Effective caching strategies ensure that content is kept fresh, up-to-date, and consistently delivered with high efficiency.

In this section, we will explore different caching strategies used by CDNs, including time-based caching (TTL), cache invalidation, cache purging, and stale-while-revalidate. Understanding these strategies helps optimize content delivery while balancing performance and content freshness.

## 1. Time-Based Caching (TTL - Time to Live)

### How It Works:
- **Definition:** Time-based caching uses a TTL (Time to Live) value to define how long cached content remains valid before it is considered stale and must be re-fetched from the origin server. The TTL can be set for each type of content based on its characteristics (e.g., static images might have a longer TTL than dynamic content).
- **Example:** A webpage may have a TTL of 24 hours, meaning that the cached version of the page will be served to users for up to 24 hours before the CDN refreshes it from the origin.

### Benefits:
- **Improved Performance:** By keeping cached content fresh for a specified time, CDNs reduce the need to constantly request data from the origin server.
- **Efficient Resource Use:** Content that does not change frequently can be cached for longer periods, improving efficiency and reducing bandwidth usage.

### Use Case:
A blog site with static content can set long TTL values (e.g., 24 hours) for articles that rarely change, reducing the load on the origin server.

---

## 2. Cache Invalidation

### How It Works:
- **Definition:** Cache invalidation refers to marking cached content as stale before its TTL expires. This forces the CDN to fetch the latest version of the content from the origin server when a new request is made. Cache invalidation is often used when content needs to be updated more frequently than the TTL allows.
- **Example:** If a product price changes on an e-commerce site, cache invalidation ensures that users receive the updated price immediately rather than waiting for the TTL to expire.

### Benefits:
- **Ensures Freshness:** Cache invalidation allows for immediate updates, ensuring users always receive the latest version of content.
- **Fine-Grained Control:** You can selectively invalidate specific pieces of content without affecting other cached resources.

### Use Case:
An online store can use cache invalidation to update product listings, ensuring that prices and stock availability reflect the most recent data.

---

## 3. Cache Purging

### How It Works:
- **Definition:** Cache purging involves clearing the entire cache for specific content or across all edge servers. This action forces the CDN to retrieve fresh copies of the content from the origin server on subsequent requests. Purging is typically used in emergency scenarios or after significant changes to the website or application.
- **Example:** After launching a new version of a website, cache purging ensures that users are served the updated version instead of outdated cached pages.

### Benefits:
- **Full Refresh:** Purging clears out all cached versions of specific content, ensuring that users receive the most up-to-date version.
- **Critical for Major Updates:** Cache purging is useful after large-scale changes, such as a complete site redesign or after fixing critical bugs.

### Use Case:
A media company that has rebranded its entire website can use cache purging to clear old design elements from the cache and serve the latest content to users.

---

## 4. Stale-While-Revalidate

### How It Works:
- **Definition:** The stale-while-revalidate strategy allows the CDN to serve stale content to users while it fetches a fresh version from the origin server in the background. This ensures that users don’t experience delays while the content is updated.
- **Example:** If a webpage's cache has expired, the CDN will still serve the stale page while it revalidates the content in the background, ensuring that future users receive the updated version without delays.

### Benefits:
- **Reduced Latency:** Users experience no delay because the CDN serves stale content while it retrieves fresh data in the background.
- **Improved User Experience:** Stale-while-revalidate ensures that users always receive content instantly, even when the cache is expired.

### Use Case:
An online newspaper can use stale-while-revalidate to ensure that users always receive content quickly, even if the cached version is slightly out-of-date, while the updated articles load in the background.

---

## 5. Cache Prewarming

### How It Works:
- **Definition:** Cache prewarming involves proactively populating the cache with content before it is requested by users. This technique is often used for content that is expected to be in high demand, ensuring it is ready to be served from edge servers when traffic spikes occur.
- **Example:** Before launching a new product, an e-commerce platform might prewarm the cache with product images, descriptions, and other static content to ensure it loads quickly during the initial surge of user traffic.

### Benefits:
- **Preparedness for High Demand:** Cache prewarming ensures that popular content is ready to be served immediately, reducing latency during traffic spikes.
- **Optimized Resource Allocation:** By anticipating demand, prewarming helps avoid sudden increases in load on the origin server during peak traffic times.

### Use Case:
A streaming service might prewarm its cache with the video assets of a newly released movie to ensure smooth and fast streaming during the initial release.

---

## Conclusion

CDN caching strategies are essential for optimizing performance and ensuring that content is delivered efficiently and consistently. By implementing time-based caching, cache invalidation, purging, and stale-while-revalidate techniques, you can control content freshness while minimizing latency and server load. Understanding and utilizing these strategies effectively allows you to balance content performance with user experience.

---

[Next: 9.4. Security Features in CDNs](./section_9_4.md)
