---
tags:
  - interview
  - architecturalParadigm
author:
  - jacgit18
Status: Refinement
Started: 2024-01-04
EditDate: 2024-01-16
Relates: 
Comments: Still cleaning up this process flow maybe can convert to a mind map or something visual.
---
![[System design core concepts.gif]]
### **Step 1: Understand the Problem and Establish Design Scope (3 - 10 minutes)**
During this step, it's crucial to clarify the system scope and priorities and gather [[Business Requirements Life cycle|Business Requirements]]. For instance, if asked to design an Instagram Reels feature, break down the problem into specific use cases, outlining interactions between system components. Identify key requirements like expected traffic, data volume, latency, and scalability. Inquire about the [[Userbase]] type which can give you insight for things like estimating resources  or  things like governance, like what if user base  is under aged, as this is crucial for scalability considerations. Understand potential constraints and bottlenecks that may arise with a growing user base. This leads to decisions on database considerations, determining whether a NoSQL or SQL database aligns with specific needs and the nature of the data.
#### [[Use Case vs User Story |User Story]] Example:
>[!important]
>Creating stories helps with building data model, also if dealing with complex feature might want to consider using Use Cases over Stories.
1. As a user I want to upload picture and videos to share.
2. As a user I want to view uploaded photos and videos.
3. As a user I want to follow, like, and comment on posts.
4. As a user I want to see a feed containing posts from friends.
5. As a user I want to block or unfollow other users.

### Step 2: Design Deep Dive (15 - 25 minutes)
>[!important]
When considering the features of your design, prioritize a forward-thinking approach that allows for future functionality. Ensure your design is flexible, accommodating potential expansions and enhancements seamlessly. Focus on building a foundation that supports scalability, making it easier to integrate additional features in the future. Think holistically about the design, anticipating potential modifications and advancements, and ensure that the architecture is adaptable to evolving requirements. This foresightedness will contribute to a more sustainable and extensible system over time.

*Delve into the design by following the flow from Database to Server/Services (Architecture) to Client Side design.

For more info read [[System Design Interview An Insider’s Guide.pdf]] and [[System Design Interview - An Insider's Guide Second Edition|System Design notes]] on this book.
### Database Architecture
  - Create an Entity Relationship Diagram (ERD) to define relationships.
  - Consider SQL for structured data and NoSQL for unstructured data.
  - More things to think about when deciding between [[Choosing Database]] you can also talk about [[Database Sharding]]
  - What type of [[Schema Design]] makes sense.
  - You can also talk about [[Master-Slave Database Architecture]]
  - ????? [[File System Storage]] ??????


### Overall Architecture
  - Identify major components: physical or virtual servers, databases, [[Caches]],  [[Messaging systems]], *monitoring/logging for metrics*, and [[Benefits of cloud |cloud infrastructure]] talking about cloud  in terms of outsourcing functionality or infrastructure using different service architecture ranging from IAAS to SAAS.
  - If your thinking of other [[Architectural Styles]] identify it then talk about it.
  
**Maybe refine a little more **
  - Networking components such as routers, [[Load Balancer]], firewalls, and Content Delivery Networks ([[Content Delivery Network |CDN]]) play a crucial role in ensuring that data is transmitted efficiently between clients and servers. Load balancers distribute incoming traffic to multiple servers for load distribution and redundancy.
  - Security measures like firewalls, intrusion detection systems, encryption, and access control mechanisms are part of the Infrastructure layer to protect the application from various security threats, including unauthorized access, data breaches, and DDoS attacks.
  - **Compliance and Governance**: Infrastructure may include tools and processes to enforce compliance with regulatory requirements and organizational policies, ensuring data security and legal compliance.

  - Discuss trade-offs between performance, scalability, and cost.
  - Maybe CI/CD stuff
  - Consider the use of APIs for certain functionalities.
  - Discuss [[Stateless & Statefull Processes |Stateless vs Statefull]] application or process.
  - Maybe talk [[Microservices]](might not be relevant since small scope) or leverage knowledge of [[12 Factor App Docker.canvas|12 Factor App Docker]] which has some overlap with everything mentioned, whatever comes to mind.
  - Making [[Event-driven Architectural Pattern Decisions]].

### Scalability and Performance
  - Distribute traffic across server pools for different types of traffic.
  - Implement local cache for improved response time.

  - You can talk about [[Vertical vs Horizontal Scaling]] in the context of database servers and instances of your application along with any microservices if you include that in your codebase architecture. Side note scaling can fall under Admin functionality weather that is resource scaling in a cloud environment or some custom built solution like creating an admin dashboard for internal use by developers with a frontend that includes different [[XII Admin processes]].
  - Horizontal scaling is often more desirable since vertical scaling limitations like it is impossible to add unlimited CPU and memory to the server and it lacks fail over and redundancy if one server goes down the website app goes down with it completely 

  


#todo/Low/Research
- [ ] Talk about centralized systems in comparison to decentralized systems which is mostly covered here need to research more about centralized systems 



### Step 3: Wrap Up(3 - 5 minutes)
Summarize key design decisions, highlighting any alternative considerations. Invite questions and address outstanding concerns.

# Talking Stats  
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

## Traffic Estimate Example:

### Network Traffic Estimate Example:
- Active users Posting: 10 million `POST Request`
- User Post viewed: 30 views per user or 30 `GET Request`
- GET traffic = 300 million (10 million * 30)
- `GET Requests` total traffic per second: 3,000 (300 million / 86,400 seconds)
- Active user `POST Request` per second: 115 (10 million / 86,400 seconds)

### Memory Storage Estimate Example:
- Cache for Instagram highlights: 150 GB (300 million requests * 500 bytes)
- Adjusted cache: 30 GB (20% of 150 GB)
- Total memory: 90 GB (30 GB * 3 for replication)

### Bandwidth:
- Bandwidth required: 450,000 GB (300 million(Active users) * 1.5 MB)
- Bandwidth per second: 5.2 GB (450,000 GB / 86,400 seconds in a day)

### Storage:
- Daily storage for writes: 15 TB (10 million writes * 1.5 MB)
- Yearly storage: 55 PB (15 TB * 365 days * 10 years)

### Summary:
- Traffic: Daily active users * average reads and writes per user
- Memory: Read requests per day * average request size * 20%
- Bandwidth: Requests per day * average request size
- Storage: Writes per day * size of write * time to store data


# Alt Design
### Music Streaming Service Estimation:

**Assumptions:**
- Average song duration: 3 minutes
- Average songs played per hour per user: 20 songs
- Average daily active users: 10 million
- Average hours of music played per user per day: 3 hours
- Number of days in a month: 30

#### Math Problem:

1. **Daily Usage Estimation:**
   - Songs played per user per day: 20 songs/hour * 3 hours = 60 songs
   - Total daily songs played: 60 songs/user * 10 million users = 600 million songs
   - Total daily music duration: 600 million songs * 3 minutes/song = 1,800 million minutes

2. **Monthly Usage Estimation:**
   - Total monthly music duration: 1,800 million minutes * 30 days = 54,000 million minutes

3. **Conversion to Seconds:**
   - Total monthly music duration in seconds: 54,000 million minutes * 60 seconds/minute = 3,240,000 million seconds

### Why This Information Matters:

**Throughput Considerations:**
- The system needs to handle a massive volume of song requests and streaming data.
- Infrastructure must support concurrent users and maintain low latency during high usage periods.
- Designing the database, server architecture, and network bandwidth should accommodate this estimated daily and monthly load.
- Ensuring scalability is crucial to handle potential growth in user base and usage patterns.

This estimation allows us to properly design and dimension the infrastructure to meet the demands of the music streaming service, ensuring a smooth and responsive user experience.



![[System Design Cheatsheet.gif]]


![[System Design BluePrint.jpg]]

## Advance Roadmap
![[system-design.pdf]]