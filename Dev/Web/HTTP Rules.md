Rule: GET and POST must not be used to tunnel other request methods 

Rule: HEAD should be used to retrieve response headers 

Rule: PUT must be used to update mutable resources 

Rule: POST must be used to execute controllers 

Tunneling refers to any abuse of HTTP that masks or misrepresents a message’s intent and undermines the protocol’s transparency. A REST API must not compromise its design by misusing HTTP’s request methods in an effort to accommodate clients with limited HTTP vocabulary. Always make proper use of the HTTP methods as specified by the rules in this section.



request method can be safe, idempotent, or cacheable. 

[https://developer.mozilla.org/en-US/docs/Glossary/Safe/HTTP](https://developer.mozilla.org/en-US/docs/Glossary/Safe/HTTP)  

[https://developer.mozilla.org/en-US/docs/Glossary/Idempotent](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent) 

[https://developer.mozilla.org/en-US/docs/Glossary/cacheable](https://developer.mozilla.org/en-US/docs/Glossary/cacheable)