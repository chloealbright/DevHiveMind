---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


-   Append-Only-Log 
    
    -   For applications with clearly defined edits, or applications where clients really shouldn’t be touching values directly, it may be worth doing away with the traditional update-with-new-value operation entirely. 
        
    -   Same as timestamp-checked: Store both the resource’s current value and a timestamp for the most recent write. Then expose two (or three) operations: 
        
    -   Read-Return-Timestamp: Same as timestamp-checked, return the resource’s current value and timestamp. 
        
    -   Append-Return-Updated: Instead of providing the value to write to the service, the service defines a set of edit operations that can be applied to its resources. The clients then provide one of those operations to the service to run on the resource. The updated value is then returned to the client. 
        
    -   Load-Since-Timestamp: Optional operation. Suppose clients are capable of computing the results of edit operations themselves. In that case, clients can provide the timestamp of their most recent read of a resource and then receive all edit operations that have been applied to the resource since that timestamp. 
        
    -   Operational Transforms and CRDT-based applications are perhaps the most advanced applications of this pattern, which is used extensively in our collaboration apps. Simpler ones exist, such as a banking API that allows you to withdraw, deposit, and transfer money but not manually set your account balance. 
        
    
-   Considerations 
    
    -   Two things to note about the above patterns: 1) I did not include the search or re-ACL/hard-delete operations for any of these, since they’re common to all approaches and largely unaffected by which pattern you pick; and 2) these patterns are not mutually exclusive — it is entirely possible to have an API with a create-unless-exists and update-check-timestamp operation, for example. 
        
    -   None of this is to say that CRUD has no place in service API design — only that it should not be the pattern of first-resort. In particular, CRUD is useful when a client considers the creation or destruction of a resource meaningfully significant and different from editing that resource, or when the service needs to do significant validation or computation that is not necessary on edit. 
        
    -   A few examples include situations where the primary key of a resource consists of real-world information, such as a social security number where resource key collisions are possible and dangerous, whether accidental or malicious. Another could be where create operations accept substantially more information than updates, such as creating an online food order vs. changing the driver’s tip. 
        
