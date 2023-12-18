---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
differences between the various event-driven API options. | Example services 

-   WebHooks 
    
    -   Event notification via HTTP callback   | Slack, Stripe, GitHub, Zapier, Google 
        
    -   Easy server-to-server communication 
        
    -   Uses HTTP protocol 
        
    -   Do not work across firewalls or in browsers 
        
    -   Handling failures, retries, security is hard 
        
    -   Used To trigger the server to serve real-time events 
        
    
-   WebSockets 
    
    -   Two-way streaming connection over TCP  |  Slack, Trello, Blockchain 
        
    -   Two-way streaming communication 
        
    -   Native browser support 
        
    -   Can bypass firewalls 
        
    -   Need to maintain a persistent connection 
        
    -   Not HTTP 
        
    -   Used For two-way, real-time communication between browsers and servers 
        
-   HTTP Streaming 
    
    -   Long-lived connection over HTTP   |  Twitter, Facebook 
        
    -   Can stream over simple HTTP 
        
    -   Native browser support 
        
    -   Can bypass firewalls 
        
    -   Bidirectional communication is difficult 
        
    -   Reconnections required to receive different events 
        
    -   Used For one-way communication over simple HTTP 
        
-   There is no one-size-fits-all solution when it comes to selecting an API paradigm. Each of the API paradigms that we discussed in this chapter works well for certain kinds of use cases. You might need to support multiple paradigms, too. For example, the Slack API supports RPC-style APIs, WebSockets, and WebHooks. It’s important for you to understand which solution will work best for your customers, which will help you meet your business goals, and what is possible with the constraints within which you are working.