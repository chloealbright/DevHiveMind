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