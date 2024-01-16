---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
A Content Delivery Network (CDN) is a network of dispersed servers that efficiently delivers static content like images, videos, and scripts. It can also cache dynamic content, such as HTML pages based on request attributes.

When a user accesses a website, the CDN server closest to them delivers static content, optimizing loading speed. If the CDN lacks the requested content, it fetches it from the origin, like a web server or Amazon S3. The origin returns the content, specifying a Time-to-Live (TTL) for caching. The CDN caches and serves the content until TTL expiration.

Considerations for CDN usage include cost, setting appropriate cache expiry times, handling CDN fallback during outages, and methods for invalidating files. CDNs improve performance by offloading static asset serving, reducing database loads through caching, and supporting millions of users through scalable system practices like stateless web tiers, redundancy, and multiple data centers.

In scaling systems for millions of users:
- Maintain stateless web tiers
- Incorporate redundancy at every tier
- Maximize data caching
- Support multiple data centers
- Host static assets in CDNs
- Scale the data tier through sharding
- Divide tiers into individual services
- Monitor the system and leverage automation tools.


Yes, in a sense, a CDN (Content Delivery Network) can be considered a network of web servers. However, there is a distinction in their primary functions:

- **Web Servers:** Typically concentrate on handling dynamic content, processing requests, and managing server-side logic. They may be centralized in a data center.

- **CDN:** Comprises a distributed network of servers strategically located in various geographic locations. While these servers can serve static content like web servers, the primary focus of a CDN is to optimize the delivery of content by caching and serving it from the server closest to the user, reducing latency and improving performance.

So, while both involve servers, a CDN's emphasis is on content delivery optimization through distribution, caching, and proximity to end-users.