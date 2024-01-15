---
tags: 
author:
  - jacgit18
Status: Capture
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