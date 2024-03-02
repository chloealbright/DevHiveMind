---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
SAGA is one of the best solutions to keep consistency with data in distributed architecture without having the ACID principles. SAGA is responsible for committing multiple commentary transactions by giving rollback opportunities.

  

There are two ways to achieve the saga's

  

1. Choreography

2. Orchestration.

In this choreography saga, there is no central orchestration. Each service in the Saga carries out its transaction and publishes events. The other services respond to those occurrences and carry out their tasks. In addition, depending on the scenario, they may or may not publish additional events.

In the Orchestration saga, each service participating in the saga performs their transactions and publish events. The other services respond to those events and complete their tasks.

#### Advantage of using SAGA 

1. Can be used to maintain the data consistency across multiple services without tight coupling.

  

#### The disadvantage of using SAGA

1. Complexity of the SAGA design pattern is high from the programmer's point of view and developers are not well accustomed to writing sagas as traditional transactions.


