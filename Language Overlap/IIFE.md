---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
IIFE(Immediately invoked function expression) create a function that automatically is called

```javascript

(function () { 

  /* ... */ 

})(); 

```

```javascript

// Arrow function IIFE 

(() => { 

  /* ... */ 

})(); 

```

```javascript
// async IIFE 

(async () => { 

  /* ... */ 

})(); 

```

```

// recursion 

(function myIIFFE () { 

++num 

log(num) 

return num !== 5 ? myIIFFE(num) : log("finish") 

})(num = 0); 

const x = "whatever"  

const helloWorld = () =>  { 

"Hello" 

} 

(() { 

const x = "life" 

const helloWorld = () =>  { 

"Hello Life" 

} 

log(x) // first return 

log(helloWorld()) // second return 

})(); 

log(x) // third return 

log(helloWorld()) // fourth return 

const increment = (() => { 

let count = 0 

log(count) 

const credits = (num) => log(`I have ${num} credits` ) 

return () => {++count; credits(count) } 

})(); // returns just counter value  

increment() // returns anonymous function value  

I have 1 credit 

increment() // returns anonymous function value  

I have 2 credit 

credits(3) // returns error  because closure rule  

// module pattern  

const Score = (() => { 

let count = 0 

return { 

current: () => { return count }, 

increment: () => {  ++count }, 

reset: () => {  count = 0 }, 

 } 

})();  

Score.increment() 

log(Score.current()) 

// module pattern variation with pointers work like other example 

const Game = (() => { 

let count = 0 

return { 

current: current, 

increment: increment, 

reset: reset 

 } 

})();  

Score.increment() 

log(Score.current()) 

// inject a namespace object 

((namespace) => { 

namespace.count = 0 

namespace.current = () =>{ return `App count is ${this.count} ` } 

namespace.increment =  () =>{  this.count++} 

namespace.reset =  () =>{ this.count = 0} 

})(window.App = window.App || {} );  

App.increment() 

log(App.current()) 

https://flaviocopes.com/javascript-iife/