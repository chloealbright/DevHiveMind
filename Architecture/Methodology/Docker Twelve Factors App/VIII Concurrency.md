---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Concurrency: The app should scale out horizontally by adding more processes, rather than increasing the size of individual processes. Docker's orchestration tools (Kubernetes, Nomad, Swarm, etc) can automatically manage the scaling of your app based on defined rules and resource utilization.

In the context of the springboot app from Cre8tive the [[Eureka service]] helps with concurrency.

## Relating Topics
[[Concurrency Vs Horizontal Scaling]]
[[Concurrent programming]]


![[Twelve Factor App Concurrency]]