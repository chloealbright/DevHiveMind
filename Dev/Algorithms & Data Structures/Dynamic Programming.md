![[unnamed (40).gif]]

might come up for higher-level companies and fang


Divide&Conquer(includes Recursion) + memoization = Dynamic programming  
  
divide into sub-Problems occur frequently -> solve with recursion -> memioze subproblems and store  
  
  
  
Dynamic Programming is just an optimization technique that uses caching so it means nothing actually means nothing it is just a garbage buzzword.  
  
  
If you have something that you can cache Well then he can use dynamic programming.  
  
level dynamic programming is a way to solve problems by breaking them down into a collection of subproblems  
  
solving each of those solve problems just once and storing their solutions in case.  
  
Next time the same subproblem occurs but let's get into that and understand what it means how we can  
  
implement it to become better interviewers better engineers and better programmers.  
  
in dynamic programming, there is a pattern that is always there  
  
  
You can rewatch the video  
  
One is that you can't think of dynamic programming as combining divide and conquer.  
  
What we did in the example with the tree-like structure of Fibonacci number where we use recursion and using reuse that is cashing in memoization with recursion to get savings in performance and use dynamic programming. And these are the steps that are like to follow to see if a problem can use dynamic programming to optimize it.  
  
We first ask can the problem be divided into subproblems that is it a tree-like structure where each problem is broken down into smaller problems and do small problems which usually indicate a recursive solution.  
  
There can also be tree-like structures that don't have repetitive subproblems.  
  
But if these subproblems are repetitive that is that we're doing the same calculation over and over in the subproblems. we can memorize these subproblems and once we do that we see tremendous benefits and these benefits are used all over computer science to improve performance so that the fifth step should be to demand a raise from your boss.  
  
If you've implemented this because you've just saved so many calculations so much time complexity I want you to think like this instead of being intimidated by the confusing name that is dynamic programming you just need to know when a problem can use this technique. And at least some problems for you after this section to practice on but you want to just follow this pattern.  
  
When a problem has solutions composed of solutions to the same problem with smaller and smaller inputs each problem is solved only once and the result of each subproblem is stored in a table like a cache such as a hash table.


# Example
we can approach this two ways either  a top-down approach were use a combination of closure, recursion, and memorization I feel like this is possibly better if were using a tree that doesn't have a lot of depth  

```javascript
top-down approach 

function fibonacciMaster() { //O(n) 

  let cache = {}; 

  return function fib(n) { 

    calculations++; 

    if (n in cache) { 

      return cache[n]; 

    } else { 

      if (n < 2) { 

        return n; 

      } else { 

        cache[n] = fib(n-1) + fib(n-2); 

        return cache[n]; 

      } 

    } 

  } 

} 

or 

bottom up approach 

function fibonacciMaster2(n) { 

  let answer = [0,1]; 

  for ( let i = 2; i <= n; i++) { 

    answer.push(answer[i-2]+ answer[i-1]); 

  } 

  return answer.pop(); 

} 
```
