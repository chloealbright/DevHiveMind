![[unnamed (48).gif]]

used in Dynamic programming


In order to understand how dynamic programming works we need to understand what caching means.  
  
Caching is a way to store values so you can use them later on.  
  
Ideally, you can think of caching as a backpack where you take the books you need for school instead of going back home all the time to get the books when you need a specific book or something like a pencil. You have a small box on your back that holds items that you need so that when you go to school you can just reuse them fast over and over.  
  
  
Caching is just a way for us to speed up programs and hold some piece of data in an easily accessible box and memoization is a specific form of caching that used a lot in dynamic programming.  
  
let's imagine we have a function that says we want to add to 80 and this function takes a number and all it does is return the value of it plus the parameter we give it.  
  
So that when we run the function add to 80 and let's say we put in five we get 85 but if we run the function again, we'll have to go through this step again and add 80 to that answer.  
  
but if call the function three times it takes a long time. because every time you run this function we'll have to run a long time three times and go through the step one by one.  
  
Even though we've done the exact same calculation three times Is there a way that we can optimize this.  
  
this is where we can use caching and memoization  
  
you can create a new object called Cache that's going to hold an empty object. We're also going to have a function that handles the memorized process.  
  
  
let's say that if n is in the cache and this is a way to check if a property exists in an object.  
  
So if an exists in the cache.  
  
So if we've cashed it before then simply return the cache and so return the cached value.  
  
But obviously, it's empty.  
  
The first time around so this is not going to work if there's nothing in the cache which is the case  
  
the first time around.  
  
Well we have an else statement and in here we're going to have our cache which doesn't exist yet and assign it a plus 80  
  
We go through the if statement find the fact that we've already calculated five and just do simple property  
  
access which as we know is of one time is super fast with a hash table like this.  
  
  
memoization is a specific form of caching that involves caching the return value.  
  
All the function that is the return value of this function based on its parameters.  
  
And if the parameter of this function doesn't change like it is here then it's memorized.  
  
That is it uses the cache because it's calculated the same thing before with the same parameter and  
  
it will return a cached version of the function.  
  
It's memorized if the parameter changes.  
  
memoization is simply a way to remember a solution to a solved problem.  
  
So you don't have to calculate it again.  
  
  
You see ideally we don't want to fill the cache in what we called the global scope.  
  
That is to be living outside of this function.  
  
Ideally, it's good practice to have memory or in this case the cache to live inside of this function not  
  
polluting the global scope.  
  
And there are many ways to do this based on the language in javascript that we can use something called  
  
closures.  

```javacript
// A memoize decorator function  
// that is capable of handling multiple parameters  
export const memoize = (fn) => {  
const cache = {};  
  
return (...args) => {  
if (JSON.stringify(args) in cache) {  
// if you want to verify result comes from cache  
console.log(cache);  
return cache[JSON.stringify(args)];  
}  
const result = fn(...args);  
cache[JSON.stringify(args)] = result;  
return result;  
}  
}

```
