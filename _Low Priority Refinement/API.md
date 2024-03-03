---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---

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

