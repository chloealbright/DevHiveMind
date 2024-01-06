---
tags:
  - interview
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
**Step 1: Understand the Problem and Establish Design Scope (3 - 10 minutes)**
- Define `useCases`/`userStories`
- Seek clarification on scope and priorities.

**Step 2: Propose High-Level Design (10 - 15 minutes)**
- High-level components.
- List the major components that the system will need. These might include servers, databases, cache, load balancers, messaging queues, maybe microservices etc whatever your familiar with.

**Step 3: Design Deep Dive (10 - 25 minutes)**
- Entity Relationship Diagram (ERD).
- Diagram defining relationships.
- Discuss stateless application service with microservices, servers, cache servers.

**Step 4: Wrap (3 - 5 minutes)**
- Summary of key design decisions.
- Ask about any outstanding concerns.

### Use Cases/Stories:

1. User uploads pictures or videos.
2. User views uploaded photos and videos.
3. User follows, likes, and comments on posts.
4. User has a feed containing posts from friends.
5. User can block or unfollow other users.

### Entity Relationship Diagram (ERD):

- Discuss relationships among entities.

### High-Level Components:

- Client-side > Server/services (Architecture) > Database.
- Consider SQL for structured data or NoSQL for unstructured data.

### Stateless Architecture:

- Application service with microservices.
- Stateless app servers accessing other services via API.

### Load Balancer and Cache:

- Multiple load balancers for different types of traffic.
- Local cache for improved response time.
- CDN network for content distribution.

### Traffic Estimates:

- Estimate read and write requests per second.
- Calculate memory, bandwidth, and storage requirements.

### Bandwidth and Storage Estimates:

- Detailed calculations for bandwidth and storage requirements.

### Summary:

- Daily traffic, memory, bandwidth, and storage calculations.
- Emphasize the need for redundancy, scalability, and monitoring.
  
### Alternative Summary:

- Breakdown of traffic, memory, bandwidth, and storage requirements.
- Conversion of units for better readability.
- Key emphasis on the importance of scalability and redundancy.