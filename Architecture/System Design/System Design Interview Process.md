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
- Ask question to get clarification on scope and priorities.
- Break down the problem into distinct use cases / user stories.
- Understand the interactions between different components of the system based on these use cases.
- Clarify any ambiguities in the problem statement.
- Identify key requirements and constraints, such as expected traffic, data volume, latency, and scalability.

**Step 2: Design Deep Dive (10 - 25 minutes)**
- Focus on data come up with a Entity Relationship Diagram (ERD) defining relationships.
- Talk about potential database type you might use or when you utilize an API whatever comes to mind.
- Discuss stateless vs statefull application service with microservices, servers, cache servers etc..

**Step 3: Propose High-Level Design (10 - 15 minutes)**
- Talk about high-level components mentioning stuff about Scalability, maybe Fault Tolerance, and Security.
- List the major components that the system will need. These might include servers, databases, cache, load balancer, messaging queues, maybe microservices etc, whatever your familiar with talk about.

**Step 4: Wrap (3 - 5 minutes)**
- Summarize of key design decisions mentioning whatever else you want mention or alternative decisions.  
- Ask about any outstanding concerns.

### Use Cases/Stories Example:

1. User uploads pictures or videos.
2. User views uploaded photos and videos.
3. User follows, likes, and comments on posts.
4. User has a feed containing posts from friends.
5. User can block or unfollow other users.

### High-Level Components:

- Client-side > Server/services (Architecture) > Database.
- Consider SQL for structured data or NoSQL for unstructured data.


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

![[System Design Cheatsheet.gif]]


![[System Design BluePrint.jpg]]