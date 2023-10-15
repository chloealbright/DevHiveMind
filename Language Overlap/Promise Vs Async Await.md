A Promise in NodeJS is similar to a promise in real life. It is an assurance that something will be done. Promise is used to keep track of whether the asynchronous event has been executed or not and determines what happens after the event has occurred. It is an object having 3 states namely: 

Aysnc function returns promises so when you call it you can chain .then() and .catch() and other related methods for error handling 

When you newly create a promise it will be

PENDING: Initial State, before the event has happened. 

When a promise has been                                                                                                       RESOLVED: After the operation completed successfully. 

When an error occurred and the promised value can't be determined           

REJECTED: If the operation had error during execution, the promise fails. 

Fetch also returns promises  

Error Handling of Promises: For a successfully resolved promise, we use .then() method and for rejected promise, we use .catch() method. To run a code after the promise has been handled using .then() or .catch() method, we can .finally() method. The code inside .finally() method runs once regardless of the state of the promise. 

```javascript
const promise = new Promise(function (resolve, reject) { 

const string1 = "geeksforgeeks";                                                                                                        
const string2 = "geeksforgeeks";                                                                                                                  
if (string1 === string2)  resolve();                                                                                                                
else  reject(); 

}); 

  Promise .then(
  function (){    
    console.log("Promise resolved successfully");                   
     }) 

.catch(function () { 
   console.log("Promise is rejected");
   
   }); 
```

The promise chain is what you need when your operation consists of several asynchronous functions, and you need each one to complete before starting the next one. But there are other ways you might need to combine asynchronous function calls, and the Promise API provides some helpers for them. 

Sometimes you need all the promises to be fulfilled, but they don't depend on each other. In a case like that it's much more efficient to start them all off together, then be notified when they have all fulfilled. The Promise.all() method is what you need here. It takes an array of promises, and returns a single promise. 

The promise returned by Promise.all() is: 

fulfilled when and if all the promises in the array are fulfilled. In this case the then() handler is called with an array of all the responses, in the same order that the promises were passed into all() 

rejected when and if any of the promises in the array are rejected. In this case the catch() handler is called with the error thrown by the promise that rejected. 

```javascript
Promise.all([fetchPromise1, fetchPromise2, fetchPromise3]) 

  .then( responses => { 

    for (const response of responses) { 

      console.log(`${response.url}: ${response.status}`); 

} 

  }) 
```

Here we're making three fetch() requests to three different URLs. If they all succeed, we will log the response status of each one. If any of them fail, we're logging the failure. 

With the URLs we've provided, all the requests should be fulfilled, although for the second, the server will return 404 (Not Found) instead of 200 (OK) because the requested file does not exist.  

Sometimes you might need any one of a set of promises to be fulfilled, and don't care which one. In that case you want Promise.any(). This is like Promise.all(), except that it is fulfilled as soon as any of the array of promises is fulfilled, or rejected if all of them are rejected: 

```javascript
const fetchPromise1 = fetch('https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json'); 

const fetchPromise2 = fetch('https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/not-found'); 

const fetchPromise3 = fetch('https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json'); 

Promise.any([fetchPromise1, fetchPromise2, fetchPromise3]) 

  .then( response => { 

    console.log(`${response.url}: ${response.status}`); 

  }) 

  .catch( error => { 

    console.error(`Failed to fetch: ${error}`) 

  }); 
```

[https://medium.com/swlh/promises-async-await-and-fetch-network-requests-in-modern-javascript-fd0b2b384f3e](https://medium.com/swlh/promises-async-await-and-fetch-network-requests-in-modern-javascript-fd0b2b384f3e) 

[https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)