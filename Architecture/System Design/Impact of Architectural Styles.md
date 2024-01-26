---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates: "[[Architectural Styles]]"
Comments: This documentation discusses
---
When it comes to architectural styles they can man have a major effect on the components of a system. 

The chosen architecture significantly influences how different components interact, scale, and maintainability. Let's explore how these architectural styles affect key components:  
  
1. **Monolithic Architecture:**  
- **Components:**  
- In a monolithic architecture, all components (e.g., user interface, business logic, and data access) are tightly integrated into a single, cohesive unit.  
- **Impact:**  
- Simplifies development and deployment but can lead to challenges in scalability and maintainability as the application grows.  
- Scaling typically involves replicating the entire monolith.  
  
2. **Microservices Architecture:**  
- **Components:**  
- Decomposes the system into independently deployable and scalable services, each responsible for specific business capabilities.  
- **Impact:**  
- Enhances scalability, as individual services can scale independently.  
- Facilitates independent development and deployment of services, promoting agility.  
- Requires robust service communication mechanisms, often relying on APIs and message queues.  
  
3. **Service-Oriented Architecture (SOA):**  
- **Components:**  
- Similar to microservices but may have larger, more coarse-grained services that communicate through standardized protocols.  
- **Impact:**  
- Promotes service reusability and interoperability across different systems.  
- Centralized service orchestration may be used to coordinate interactions between services.  
  
4. **Event-Driven Architecture (EDA):**  
- **Components:**  
- Components communicate through events and event handlers.  
- **Impact:**  
- Enables loosely coupled components, making it easier to adapt and extend the system.  
- Supports real-time processing and responsiveness.  
  
5. **Serverless Architecture:**  
- **Components:**  
- Components are implemented as functions that are executed in response to events or triggers.  
- **Impact:**  
- Abstracts away infrastructure management, allowing developers to focus on code.  
- Scales automatically based on demand.  
  
6. **Layered Architecture:**  
- **Components:**  
- Divides the system into logical layers (presentation, business logic, data access).  
- **Impact:**  
- Separation of concerns simplifies maintenance and facilitates modular development.  
- Each layer can be independently replaced or upgraded.  
  
7. **Event-Driven Microservices:**  
- **Components:**  
- Combines microservices with event-driven architecture, where services communicate through events.  
- **Impact:**  
- Enhances decoupling between services, fostering flexibility and scalability.  
- Supports asynchronous communication patterns.  
  
8. **CQRS (Command Query Responsibility Segregation):**  
- **Components:**  
- Separates read and write operations, using different components for each.  
- **Impact:**  
- Optimizes performance for read-heavy or write-heavy workloads.  
- Facilitates scaling based on specific types of operations.  
  
When discussing system design, the choice of architectural style shapes the interactions, dependencies, and scalability of various components. It influences how components are developed, deployed, and maintained, impacting the overall system's agility, resilience, and ability to meet business requirements. The decision on the architectural style should align with the specific needs and goals of the project.