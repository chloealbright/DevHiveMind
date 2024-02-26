---
tags: 
author:
  - jacgit18
Comments: 
Status: 
Started: 
EditDate: 
Relates:
---


# Controller



there are two separate queries happening in all endpoint: 

Determining authorization 

Getting the data we want 

you have to be careful about thinking about them separately 

authorization is determined by company type and the users role within the company, which you get from util companyAccess 

the material data itself i think is a simple query, i dont think we’ll need to do a join




does that mean I shouldn't be assigning date_created & date_modified in the post test 

we need to overwrite company_id and created_by (submitting user's id) in the service layer 

you can, it doesnt hurt anything. but we can't expect them to equal the values output by the database, because we are overwriting them in the service layer 

users arent allowed to tell us what those fields should be




An HTTP server that listens on a specific port 

• Provides access to the HTTP Request and Response 

• A URL Router 

• Maps URL paths to our backend code 

• An interface (API) to use and write our own middleware and plugins 

• Express functions that have access to the request and response objects and act on them are    middleware 

• Express is a web server framework used to create HTTP server applications and were it  responds to requests.  

• APIs,s use a myriad of HTTP utility methods and middleware


Instead of you making a request to the API provider, the Webhook provider makes a request to you. Your code receives the request, then does something with it. Examples of Webhook requests would be Stripe sending you a notification you about a new payment or IFTTT sending you a notification of a new tweet from your Twitter account. 

WebSocket is a protocol used to establish a two-way streaming communication channel over a single Transport Control Protocol (TCP) connection. Although the protocol is generally used between a web client (e.g., a browser) and a server, it’s sometimes used for server-to-server communication, as well.


```typescript
route: '/:company_id/project/:project_id/letter/:id',  // arbritary val 
```

When strin matches route can be reasigned values but they are essential unassigned vairiable names to be references but not connected to anything






## Tacflo codebase stuff

If table doesn’t show comment out return of down in knex js and try rollback all and uncomment return of down and run latest 

wherever we have company ID as a foreign key throughout these migration files, please add an index on that field.  

// change order is a parent of letters so dont need foreign keys of company, letter, project, & action what about change order makes it the parent of letter 

only subs have crew in the context of a company  

but crew can be  but admin in other companies  

include anything not null-able in fixture  

create-companies-table 

for increment(id) dont use uuid use interger  

index is a binary tree that search   

when building db start db without foreign keys 

Monolith Api   does all api things   alternative is microservice more complicate   router what is called  every router typically have a controller   controller should(call services ) auth  data validation 

error handling  

  no side effect in controller like logging and other stuff    service handles sideEffect  

need level of detail from project team to formulate business logic 

How to structure post request to retrieve jwt



No, im not a huge fan of code coverage metrics for apps like ours. If we were making a library or a 3rd party type API it would be different 

[https://stackoverflow.com/questions/16633246/code-coverage-with-mocha](https://stackoverflow.com/questions/16633246/code-coverage-with-mocha)



similar 

router[route.method](route.route, route.controllerFn) 

get(route.route, route.controllerFn) 

router({"get", /addrandom", projectController.createRandomProject)





vision next months 

sideeffect not in controller could be in service like have service send an email or something  

the reason date_end and date_start can be modified is because they describe the ticket itself. we dont allow them to update or change date_created or date_modified because those are for our TracFlo internal use. 

things to know for interview when it comes to react  

I like react because it has a unidirectional flow from parents to children  

I hated props  

you get bugs if you have index as key so always have key 

lifeCycle methods 

hooks 

optimization pure components, memo, useMemo & callback  

use redux with redux tool on large project for sall context api and reducer 

user role 

crew 

crew members 

fxture are statc data for testng instead of dataase data whch can change  

psql -U postgres -W //login to postgresql 

figure out how to setup postgres  better 

endpoint auth wrappers on endpoints






