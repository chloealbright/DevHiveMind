---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
API's are deployed to servers. A server can provide all sorts of functionality that is not an API. For instance, you could have a server that backs up your database every 24 hours.



APIs are used to implement a protocol allowing the transfer of data across two or more applications

A server is historically the hardware on which an application runs generally meant for things like accessing your database, interacting (through APIs) with other server-based applications, and other back-end related tasks.

You’re referring to a server as an application (which is fine, btw)

An API is an Application Programming Interface, allowing (generally) a server side app to communicate with other server and front end apps.

Note, however, APIs aren’t limited to just server side apps. An API can be a communication protocol between any two applications.
#### **Infermedica API Note:**

```javascript
const axios = require("axios");

const encodedParams = new URLSearchParams();
encodedParams.append("information", "<REQUIRED>");
encodedParams.append("appId", "<REQUIRED>");
encodedParams.append("appKey", "<REQUIRED>");

const options = {
  method: 'POST',
  url: 'https://infermedicavolodimir-kudriachenkov1.p.rapidapi.com/computeDiagnosis',
  headers: {
    'content-type': 'application/x-www-form-urlencoded',
    'X-RapidAPI-Host': 'Infermedicavolodimir-kudriachenkoV1.p.rapidapi.com',
    'X-RapidAPI-Key': 'ab2ae73edamsh6e866043d798db1p1caaf7jsnc62bb5b3c241'
  },
  data: encodedParams
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

[URLSearchParams Documentation](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams)

#### **URLSearchParams Example:**

```javascript
const queryObj = {
  name: 'Dom',
  age: 45,
  occupation: 'Software Developer'
};

const usp = new URLSearchParams(queryObj);

const myname = usp.get('name');
console.log(myname);

usp.set('name', 'joe');
usp.set('youtube', 'dcode');

for(const [key, value] of usp){
  console.log(key, value);
}

console.log(usp);
console.log(usp.toString());
```

#### **Understanding APIs:**


I am frustrated by most people’s shallow understanding API’s, especially the differences between declarative (“what”) and imperative (“how”) API’s, and how that impacts one’s operations. Declarative APIs are the key pillar of what many vendors call “policy” or “intent-based” networking. 

A declarative API is a desired state system. You provide a certain state you want the system to create. You don't care about all the steps needed to achieve that state. You just tell the system: "Please make sure that the state I provide will be there." 

I haven’t seen a single API call that would tell the server how to do stuff. They always tell the server what we want to get done. Admittedly, some API calls are more abstracted than others, but that’s a different story. 

Conclusion: All API calls are declarative. 

In much the same way that the imperative mood in natural languages expresses commands, an imperative program consists of commands for the computer to perform. All Create, Update, or Delete (three quarters of CRUD) API calls are executed to change the state of the system. 

In computer science, imperative programming is a programming paradigm that uses statements that change a program’s state. In much the same way that the imperative mood in natural languages expresses commands, an imperative program consists of commands for the computer to perform. 

All Create, Update, or Delete (three quarters of CRUD) API calls are executed to change the state of the system. Admittedly, some API calls tell the system what to do in vague manner, while others are more precise. 

Conclusion: Many API calls are imperative. 

Using declarative and imperative to describe API calls makes as little sense as intent-based networking (TL&DR: every configuration is an expression of our intent). 

What really matters is the level of abstraction an API call provides, and the atomicity of the requested operation. 


[Read more](https://blog.ipspace.net/2019/04/rest-api-is-not-transactional.html)

Obviously that won’t stop the vendor marketers from proudly creating slides claiming their product uses declarative API. Make sure to make fun of them whenever you see one – it probably won’t do any more harm than mr. Quixote did to the windmills, but it might feel good (he wasn’t so lucky)


#### **Backend vs. API Functionality:**

Backend applications encompass more than just APIs. They handle data processing, database management, and overall functionality. APIs, on the other hand, facilitate communication between software components. While APIs are crucial to the backend, they represent a subset designed for external communication and integration.

**1. Backend Functionality:**
- Core operations and logic.
- Data processing, business logic, database management.
- Operates behind the scenes.

**2. API Functionality:**
- Involves functions and endpoints for communication.
- Defines rules for data exchange.
- Well-defined interface for interaction.

In summary, backend functionality is broader, while APIs provide a standardized interface for communication.

