Infermedica api 

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

[https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams)







URLSearchParams 

const queryStr = name='Dom&age=45&occupation=Software+Developer' 

// better practice 

const queryObj = { 

name='Dom', 

age=45, 

occupation='Software Developer' 

} 

const usp = new URLSearchParams(queryObj); 

//const usp = new URLSearchParams(queryStr); 

const myname = ups.get('name') 

console.log(myname) 

ups.set('name', 'joe') 

ups.set('youtube', 'dcode') 

for(const [key, value] of ups){ 

console.log(key, value) 

} 

console.log(ups) 

console.log(ups.toString())









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

https://blog.ipspace.net/2019/04/rest-api-is-not-transactional.html

Obviously that won’t stop the vendor marketers from proudly creating slides claiming their product uses declarative API. Make sure to make fun of them whenever you see one – it probably won’t do any more harm than mr. Quixote did to the windmills, but it might feel good (he wasn’t so lucky)





Backend applications can include APIs, but they are not limited to just APIs. A backend application is the part of a software system that is responsible for processing data, managing databases, and performing various operations that enable the frontend or client-side of the application to function.

APIs (Application Programming Interfaces) are a means of communication between different software components, and they often play a crucial role in the backend. Backend applications frequently provide APIs to allow interaction with the system. These APIs define the methods and endpoints that can be used to request or manipulate data.

So, while APIs are an essential part of many backend applications, the backend itself can encompass a broader range of components and functionality beyond just APIs, including database management, business logic, authentication, and more.



The key distinction between backend functionality and API functionality is in their scope and purpose:  
  
1. Backend Functionality:  
- Refers to the core operations and logic that power an application.  
- It includes tasks such as data processing, business logic, database management, and overall application functionality.  
- Backend functionality doesn't necessarily have to be exposed as an API; it can operate behind the scenes to support the application's operations.  
  
2. API Functionality:  
- Specifically involves the functions and endpoints that enable communication and data exchange between different software components, systems, or services.  
- APIs define a set of rules and protocols for how external systems can interact with and utilize the capabilities of a software system.  
- APIs serve as a means for different applications to request and exchange data or services, and they often have a more defined and standardized structure compared to general backend functionality.  
  
In summary, while backend functionality encompasses all the internal workings of an application, APIs are a subset of that functionality, designed for external communication and integration with other software components or services. APIs provide a well-defined interface for interaction, making it easier for different systems to work together.