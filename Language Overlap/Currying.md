---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Currying in JavaScript 

Currying is an advanced technique of working with functions. It’s used not only in JavaScript, but in other languages as well. 

Currying is a transformation of functions that translates a function from callable as f(a, b, c) into callable as f(a)(b)(c). 

Currying doesn’t call a function. It just transforms it. 

Let’s see an example first, to better understand what we’re talking about, and then practical applications. 

We’ll create a helper function curry(f) that performs currying for a two-argument f. In other words, curry(f) for two-argument f(a, b) translates it into a function that runs as f(a)(b): 

function curry(f) { // curry(f) does the currying transform 

  return function(a=1) { 

    return function(b=2) { 

      return f(a, b); 

    }; 

  }; 

} 

// usage 

function sum(a, b) { 

  return a + b; 

} 

let curriedSum = curry(sum); 

// there are two function calls happening the func with a and b 

alert( curriedSum(1)(2) ); //3 

closure is being used to pass the function sum to curry as a callback 

we return anonymous function with a param then that returns  anonymous function with b param  then that returns the call back function sum which is represent by f and pass what 1 and 2 to sum and we return sum  

As you can see, the implementation is straightforward: it’s just two wrappers. 

The result of curry(func) is a wrapper function(a). 

When it is called like curriedSum(1), the argument is saved in the Lexical Environment, and a new wrapper is returned function(b). 

Then this wrapper is called with 2 as an argument, and it passes the call to the original sum. 

More advanced implementations of currying, such as _.curry from lodash library, return a wrapper that allows a function to be called both normally and partially: 

function sum(a, b) { 

  return a + b; 

} 

let curriedSum = _.curry(sum); // using _.curry from lodash library 

alert( curriedSum(1, 2) ); // 3, still callable normally 

alert( curriedSum(1)(2) ); // 3, called partially 

Currying? What for? 

To understand the benefits we need a worthy real-life example. 

For instance, we have the logging function log(date, importance, message) that formats and outputs the information. In real projects such functions have many useful features like sending logs over the network, here we’ll just use alert: 

function log(date, importance, message) { 

  alert(`[${date.getHours()}:${date.getMinutes()}] [${importance}] ${message}`); 

} 

log = _.curry(log); 

After that log works normally: 

log(new Date(), "DEBUG", "some debug"); // log(a, b, c) 

…But also works in the curried form: 

log(new Date())("DEBUG")("some debug"); // log(a)(b)(c) 

Now we can easily make a convenience function for current logs: 

// logNow will be the partial of log with fixed first argument 

let logNow = log(new Date()); 

// use it 

logNow("INFO", "message"); // [HH:mm] INFO message 

Now logNow is log with fixed first argument, in other words “partially applied function” or “partial” for short. 

We can go further and make a convenience function for current debug logs: 

let debugNow = logNow("DEBUG"); 

debugNow("message"); // [HH:mm] DEBUG message 

So: 

We didn’t lose anything after currying: log is still callable normally. 

We can easily generate partial functions such as for today’s logs. 

Advanced curry implementation 

In case you’d like to get in to the details, here’s the “advanced” curry implementation for multi-argument functions that we could use above. 

It’s pretty short: 

function curry(func) { 

  return function curried(...args) { 

    if (args.length >= func.length) { 

      return func.apply(this, args); 

    } else { 

      return function(...args2) { 

        return curried.apply(this, args.concat(args2)); 

      } 

    } 

  }; 

} 

Usage examples: 

function sum(a, b, c) { 

  return a + b + c; 

} 

let curriedSum = curry(sum); 

alert( curriedSum(1, 2, 3) ); // 6, still callable normally 

alert( curriedSum(1)(2,3) ); // 6, currying of 1st arg 

alert( curriedSum(1)(2)(3) ); // 6, full currying 

The new curry may look complicated, but it’s actually easy to understand. 

The result of curry(func) call is the wrapper curried that looks like this: 

// func is the function to transform 

function curried(...args) { 

  if (args.length >= func.length) { // (1) 

    return func.apply(this, args); 

  } else { 

    return function(...args2) { // (2) 

      return curried.apply(this, args.concat(args2)); 

    } 

  } 

}; 

When we run it, there are two if execution branches: 

If passed args count is the same or more than the original function has in its definition (func.length) , then just pass the call to it using func.apply. 

Otherwise, get a partial: we don’t call func just yet. Instead, another wrapper is returned, that will re-apply curried providing previous arguments together with the new ones. 

Then, if we call it, again, we’ll get either a new partial (if not enough arguments) or, finally, the result. 

Currying Alt Syntax 

The final function in the chain has access to all the arguments in the chain. 

function fakeFunction(param1){  

   //do something  

   return (param2) => {  

     //do something    

     return (param3) => {  

        return finalResult;     

     }   

   } 

} 

Like this: 

let someParam = fakeFunction(param1); 

let anotherParam = someParam(param2); 

//and then when you call it... 

console.log(anotherParam(param3)); 

function checkStock(stockID){  

   //some check code  

   if(err){throw err;}  

   return (warehouseID) => {  

      //some check code  

      if(err){throw err;} 

      return(stockDeduct)=> {  

        //some check code          

        if(err){throw err;} 

         return stockID  

                + ' from ' + warehouseID 

                + ' is reduced by ' + stockDeduct;       

      } 

   } 

} 

let orderItem298 = checkStock('FN9382')('SOUTH')(3); 

Yes, you could merge all three functions into one, but then how do you effectively detect issues every step of the way? Currying lets you do it in an elegant manner. 

But what if you’ve got more than two or three steps? Wouldn’t the nest be so deep that it starts to look like the pyramid of doom in disguise? 

This is the visual downfall of currying. 

That’s why, as awesome as currying is, you have to be selective about where you apply it. 

The point of currying is that if you don’t provide all the parameters for a function, it returns a function that tells you what’s left in the list. In a way, it is a checking method to make sure that you’ve got everything you need before you proceed. 

It can be used as a precursor before your actual function. For example: 

function prepInvoiceLine(stockID){  

   //some check code  

   if(err){throw err;}  

   return (warehouseID) => {  

      //some check code  

      if(err){throw err;} 

      return(stockDeduct)=> {  

        //some check code          

        if(err){throw err;} 

         return  

           printInvoiceLine(stockID, warehouseID, stockDeduct);      

      } 

   } 

} 

function printInvoiceLine(stockID, warehouseID, stockDeduct){  

 return stockID  

                + ' from ' + warehouseID 

                + ' is reduced by ' + stockDeduct; 

} 

let orderItem298 = prepInvoiceLine('FN9382')('SOUTH')(2); 

Other Example 

const buildSandWich = (ingredient1) =>{ 

return (ingredient2) =>{ 

     return (ingredient3) =>{ 

    return `${ingredient1}, ${ingredient2}, ${ingredient3}` 

} 

     } 

          } 

const mySandWich  = buildSandWich("Bacon")("Lettuce")("Tomato") 

console.log(mySandWich) 

const multi =  (x, y) => x*y 

const multiCurr =  x  => y => x*y // if you only pass in x you get y function y => x * y also function are being return we just dont see the keywords  

You can store  in are variable pass in second variable 

const timeTen = multiCurr(10) returns function 

timeTen(8) returns 80 

const updateElement = id => content => document.querySelector(`#${id}`) 

textContent = content 

const updateHeaderText = updateElement('header') 

updateHeaderText('Hello Dave')