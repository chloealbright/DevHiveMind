---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
-   Identification - Who is making an API request? 
    
-   Authentication - Are they really who they say they are? 
    
    -   The process of verifying who you are. Web applications usually accomplish this by asking you to log in with a username and password. This combination is checked against an existing valid username/password record to ensure the request is authentic. 
        
-   Authorization - Are they allowed to do what they are trying to do? 
    
    -   The process of verifying that you are permitted to do what you are trying to do. For instance, a web application might allow you to view a page; however, it might not allow you to edit that page unless you are an administrator. That’s authorization. 
        
    
-   Questions to Ask About User Management 
    
    -   For onboarding developers: 
        
        -   Do you already have a way to manage user accounts to reuse for your API? Do you also wish to offer OAuth keys? 
            
        -   If you have no user management at all, what does a user need to do in order to sign up to use your API? 
            
        -   Can users sign up quickly and easily using a web browser? Should they be able to? 
            
        -   Can you simplify things by defining tiers of users? 
            
        -   What kind of information do they need to access? 
            
    -   For maintaining and managing accounts: 
        
        -   Can you reset user passwords? 
            
        -   What user interface do you want to create for user management? 
            
        -   Can users manage their accounts using a website, or is there some other way? 
            
        -   Can you monitor their usage? Can they monitor it themselves? 
            
        -   Can you revoke user accounts? 
            
        -   Do you need to implement an approval or screening process? 
            
        -   Do you need reporting and analytics around users—active developers, engagement, and retention rates? 
            
    -   Integrating your API users into the rest of your business: 
        
        -   Does developer activity need to get mapped into sales, support, and ERP systems? 
            
        -   Does your API key structure enable you to map developers to applications, your customers, and their end users? 
            
        -   Does user data need to be integrated with existing profiles or user data systems? Can you use existing SSO (single sign-on) systems? 
            
        -   Can you create usage incentives by providing developers access to their own usage data? 
            
    -   Identification 
        
        -   Session-Based Authentication 
            
        -   Oauth 
            
        -   Usernames and Passwords 
            
        -   Fortify Authentication with SSL