---
tags:
  - Domain
---

Domain-driven design (DDD) is an approach to software development that focuses on understanding and modeling the core domain of a business or application. It aims to align software design with the complexities and nuances of the domain, resulting in more maintainable, flexible, and scalable systems.

Here are some key concepts and principles of Domain-driven design:

1. Ubiquitous Language: DDD promotes the use of a common, shared language between developers and domain experts. This language, known as the "ubiquitous language," is used in communication, code, and documentation. By using a consistent language, misunderstandings and gaps in communication can be minimized, fostering a deeper understanding of the domain.

2. Bounded Context: A bounded context defines a specific area or boundary within a larger system where a certain model or language is applicable. It helps manage the complexity of large domains by breaking them down into smaller, self-contained contexts. Each bounded context has its own domain model and explicitly defines the context in which its concepts, terms, and rules apply.

3. Aggregates: Aggregates are clusters of related objects treated as a single unit. They encapsulate the behavior and enforce the consistency rules within the boundaries of the aggregate. Aggregates protect the integrity of the domain by ensuring that all changes to its internal objects are made through well-defined entry points.

4. Domain Events: Domain events represent significant occurrences or facts within the domain. They capture something important that has happened and can trigger changes in other parts of the system. Domain events are often used to communicate between bounded contexts and maintain consistency across different models.

5. Domain Services: Domain services encapsulate complex domain logic that doesn't naturally belong to a specific entity or value object. They provide operations and behavior that are significant to the domain but cannot be attributed to a single object. Domain services help maintain the cohesion and encapsulation of domain concepts.

6. Strategic Design: DDD emphasizes the importance of strategic design, which involves analyzing the business context, defining bounded contexts, establishing relationships between contexts, and identifying core domain concepts. Strategic design decisions shape the overall structure and organization of the software system.

7. Tactical Design: Tactical design focuses on modeling individual domain concepts within a bounded context. It involves designing entities, value objects, aggregates, services, repositories, and other building blocks of the domain model. Tactical design ensures that the domain model reflects the business rules and processes accurately.

By applying Domain-driven design principles and practices, developers can gain a deep understanding of the business domain and create software systems that closely align with the real-world requirements. DDD encourages collaboration between domain experts and software developers, enabling the creation of more effective and maintainable solutions.



**Relationship:**

- Event storming is a technique that can be employed within the context of DDD to facilitate the exploration and understanding of the domain. It often serves as a collaborative workshop where stakeholders come together to uncover domain events and their relationships.
- DDD provides the foundational concepts and patterns for designing the actual software based on the insights gained through techniques like event storming.
- The events identified during an event storming session often become the building blocks for defining aggregates, entities, and the overall domain model in a DDD-driven development process.

In summary, event storming is a practical, collaborative activity that aligns well with the principles of DDD. It helps teams discover and model the intricacies of a domain, providing valuable insights that can be directly translated into the design and implementation of a software system using DDD principles.