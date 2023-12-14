---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates: "[[Experience Script]]"
---
Worked on the GetLetterByID endpoint, delving into the complexities of simultaneous codebase changes, including TypeScript interfaces and the incorporation of new utils, necessitating code refactoring. Faced the challenge of comprehending and efficiently reading code without initial tests, leading to the identification and visualization of the codebase structure on whiteboard.

Navigated potential pitfalls, such as issues between integration tests and endpoints, SQL fixtures, and different layers like Controller, data, model, routes, and service layer. Gained experience in reading errors across a large codebase and honed skills in debugging various parts of the system.

Recognizing the balance in learning is crucial – knowing when to seek help and avoiding the pitfalls of tackling everything independently to prevent burnout.

It's vital because not seeking help goes against the core philosophy of software development. This philosophy centers on creating efficient, reusable, and modular code. Efficiency is the key focus, and it extends beyond coding—it applies to processes within and outside coding, such as life decisions.

Imagine your brain as a program running 24/7; you'd want to use it efficiently. Focus on problem-solving without fixating on a single issue, considering the multitude of challenges. Keep in mind the importance of overcoming short-term concerns about bothering others, transitioning to asking more questions, reducing stress, enhancing mental clarity, and fostering curiosity. It's about efficiently managing the resources at your disposal.


### Tracflo Statistics

**Create Ticket Endpoint**
- No stats available for the old app, making comparisons unfeasible.

**GetAllTickets Endpoint**
- The new app exhibits slower performance at 808.00 ms, potentially due to implementation differences aimed at enhancing security.
- In contrast, the old app demonstrates quicker response times at 576.12 ms.

**GetLetterByID Endpoint**
- Given the structure where letters are collections of change orders, and change orders are collections of tickets, the absence of a setup for change orders indicates that the GetLetterByID functionality may not exist or be implemented yet.
#### **Connected Endpoints to Front-end**

**GetAllMaterial & GetAlEquipment Endpoint**
- New app response time: 4338.2 ms
- Old app response time: 8700.4 ms

**CreateMaterials & CreateEquipment Endpoint**
- New app processing time: 321.542 ms (89), showcasing a 2x faster execution.
- Old app loading time: 812.31 ms (98) due to PHP.

**EditMaterials & EditEquipment Endpoint**
- While the edit endpoint creation was successful, the connection to the front-end didn't materialize.
- The processing time for material edits on the new app was 8222.9 ms, likely similar for equipment due to their resemblance.