---
tags: 
author:
  - jacgit18
Comments: This documentation discusses
Status: Capture
Started: 2023-12-14
EditDate: 
Relates:
---
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