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
### **Step 1: Understand the Problem and Establish Design Scope (3 - 10 minutes)**
- Ask question to get clarification on scope and priorities.
- Break down the problem into distinct use cases / user stories.
- Understand the interactions between different components of the system based on these use cases.
- Clarify any ambiguities in the problem statement.
- Identify key requirements and constraints, such as expected traffic, data volume, latency, and scalability.

#### Use Cases/Stories Example:
1. User uploads pictures or videos.
2. User views uploaded photos and videos.
3. User follows, likes, and comments on posts.
4. User has a feed containing posts from friends.
5. User can block or unfollow other users.

### **Step 2: Design Deep Dive (15 - 25 minutes)**
**Follow this Flow - Database > Server/services (Architecture) > Client Side**
- Focus on data come up with a Entity Relationship Diagram (ERD) defining relationships.
- Talk about high-level components mentioning stuff about Scalability, maybe Fault Tolerance, and Security.
- List the major components that the system will need. These might include servers, databases, cache, load balancer, messaging queues, Monitoring and Logging, maybe microservices etc, whatever your familiar with talk about it.
- Talk about the trade-offs between performance, scalability, and cost.
- Talk about potential database type you might use like talk about consider SQL for structured data or NoSQL for unstructured data. 
- maybe talk about when you utilize an API whatever comes to mind.
- Discuss stateless vs statefull application service with microservices, servers, cache servers etc..

#### Things to mention 
- You can say you don't know about this but my idea is ..... 
	- this will distribute to different servers pools  
- we also need a cache probably for Likes  
- we also a couple of master DB and slaveDB  
- Multiple load balancers for different types of traffic.
- Local cache for improved response time.
- CDN network for content distribution.

### **Step 3: Wrap (3 - 5 minutes)**
- Summarize of key design decisions mentioning whatever else you want mention or alternative decisions.  
- Ask about any outstanding concerns.









### Traffic Estimates:

- Estimate read and write requests per second.
- Calculate memory, bandwidth, and storage requirements.

### Bandwidth and Storage Estimates:

- Detailed calculations for bandwidth and storage requirements.

### Summary:
- Talk about the breakdown of daily traffic, memory, bandwidth, and storage requirements.
- Emphasize the need for redundancy, scalability, and monitoring



## Talking Stats
### Data Size:
| Unit          | Equivalent in Bytes                    |
|---------------|----------------------------------------|
| 1 Kilobyte    | 1,024 Bytes                             |
| 1 Megabyte    | 1,024 Kilobytes = 1,048,576 Bytes       |
| 1 Gigabyte    | 1,024 Megabytes = 1,073,741,824 Bytes    |
| 1 Terabyte    | 1,024 Gigabytes = 1,099,511,627,776 Bytes|
| 1 Petabyte    | 1,024 Terabytes = 1,125,899,906,842,624 Bytes|
### Time:
| Calculation                            | Result                       |
|----------------------------------------|------------------------------|
| 60 seconds * 60 minutes                | 3,600 seconds per hour       |
| 3,600 seconds * 24 hours               | 86,400 seconds per day       |
| 86,400 seconds * 30 days               | 2,592,000 seconds per month  |

### Number Places:
- 300 hundred
- 600,000 thousand
- 900,000,000 million
- 120,000,000,000 billion
- 150,000,000,000,000 trillion

### Traffic Estimate Example:
- Active users Posting: 10 million `POST Request`
- User Post viewed: 30 views per user or 30 `GET Request`
- GET traffic = 300 million (10 million * 30)
- `GET Requests` total traffic per second: 3,000 (300 million / 86,400 seconds)
- Active user `POST Request` per second: 115 (10 million / 86,400 seconds)

### Memory:
- Cache for Instagram highlights: 150 GB (300 million requests * 500 bytes)
- Adjusted cache: 30 GB (20% of 150 GB)
- Total memory: 90 GB (30 GB * 3 for replication)

Bandwidth:

- Bandwidth required: 450,000 GB (300 million * 1.5 MB)
- Bandwidth per second: 5.2 GB (450,000 GB / 86,400 seconds)

Storage:

- Daily storage for writes: 15 TB (10 million writes * 1.5 MB)
- Yearly storage: 55 PB (15 TB * 365 days * 10 years)

Summary:

- Traffic: Daily active users * average reads and writes per user
- Memory: Read requests per day * average request size * 20%
- Bandwidth: Requests per day * request size
- Storage: Writes per day * size of write * time to store data

![[System Design Cheatsheet.gif]]


![[System Design BluePrint.jpg]]