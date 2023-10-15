-   Get-and-Set 
    
    -   This is the simplest solution and one, I would argue, API designers should always consider. It consists of two operations: 
        
    -   Get: Same as CRUD’s Read. Return the most recent value for a resource, null if it doesn’t exist. 
        
    -   Set: The omnibus create/update/delete, also known as last-write-wins. Set the resource to the provided value. If the provided value is null, delete it. If two differing set operations arrive concurrently, pick a “latest” to win. Optionally, also return its previous value. 
        
    -   Most file-service APIs natively follow this pattern. For example, indexing workflows, such as indexing database objects into ElasticSearch, follow this model. 
        
    
-   Get-and-Patch 
    
    -   For resources that are divisible into multiple fields that can be updated separately, get-and-set can be easily expanded into a slightly different pattern. Get-and-Patch consists of two operations: 
        
    -   Get: Same as Get from get-and-set. 
        
    -   Patch: An omnibus create/update/delete operation, but one that allows you only to set some of the fields on a resource. Missing fields mean “keep the existing value.” Deleting a resource is done via a synthetic “deleted” field. 
        
    -   We use this pattern extensively for our configuration service APIs. JSON Patches are an example of this as well. 
        
-   Timestamp-Checked 
    
    -   For applications that follow the three-step read-compute-update pattern or otherwise require transactions or protection from concurrent edits, use logical clocks to allow for optimistic concurrency. 
        
    -   In addition to each resource’s current value, store a timestamp of the most recent write to that resource. Then expose two operations: 
        
        -   Read-Return-Timestamp: Similar to Get, but also return the timestamp of the most recent write. 
            
        -   Write-Check-Timestamp: Similar to Set, but in addition to providing the new value, also provide the timestamp that the client first read the resource. If the resource’s service-side timestamp matches the provided timestamp, execute the write and return the new timestamp. If the timestamps are different, reject the write and return the service’s value so that the client may rerun its computation and resubmit an updated value. 
            
-   You can also think about this as a variant of Check-and-Set (CAS). Firebase’s firestore API also includes this pattern as a preconditions check. 
    
-   Like most optimistic concurrency patterns, this approach has limitations; if expected concurrency is too high or if clients have expensive computations, this could result in too much lost work in retries. In these cases, it may be best to pick a different pattern and add transactional APIs around it. 
    

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
        
    
-   [https://techbeacon.com/security/critical-api-security-risks-10-best-practices#:~:text=The%20most%20critical%20API%20security,and%20insufficient%20logging%20and%20monitoring](https://techbeacon.com/security/critical-api-security-risks-10-best-practices#:~:text=The%20most%20critical%20API%20security,and%20insufficient%20logging%20and%20monitoring).