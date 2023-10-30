---
tags:
  - DP
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
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






### Top-Down vs. Bottom-Up

- **Top-Down**: Starts from a bigger, more abstract picture and works towards smaller details. It's recursive and can exceed the call stack with large values. Memoization is recommended for pure functions where inputs result in predictable outputs.

- **Bottom-Up (Tabulation)**: Is iterative and often faster, especially with large values. It's data-driven and uses known information to compute unknown values. It follows a different approach where you first address unknown indices and then use known values to fill in the gaps.

For more information on dynamic programming patterns, you can refer to this [resource](https://mageswaran1989.medium.com/a-mind-map-of-dynamic-programming-patterns-to-ace-interviews-72ff0370bb27).


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




Memoization and dynamic programming are closely related techniques in computer science, particularly in the context of algorithm optimization. Here's an explanation of their relationship:

1. **Definition**:

   - **Memoization** is a technique for optimizing algorithms by storing and reusing previously computed results. It's often used in recursive algorithms, and it involves keeping a "memo" (a cache or table) to store the results of expensive function calls and returning the cached result when the same inputs are encountered again.

   - **Dynamic Programming** is a problem-solving technique that involves breaking down a problem into smaller subproblems and solving each subproblem only once, storing their solutions in a table (usually an array or matrix). Dynamic programming is typically used for optimization problems, where you aim to find the best solution among a set of possible solutions.

2. **Relationship**:

   - **Memoization as a Subset of Dynamic Programming**: Memoization is a specific application of dynamic programming. It is essentially a top-down approach in dynamic programming, where you break down a problem into smaller subproblems and cache their solutions to avoid redundant computations. When you use memoization, you are still using dynamic programming principles but with a focus on recursion and caching.

   - **Use of Subproblems**: Both memoization and dynamic programming rely on the concept of breaking complex problems into smaller, overlapping subproblems. They both aim to solve each subproblem only once and store the results to avoid recomputation.

   - **Optimization**: Memoization and dynamic programming are used to optimize algorithms by reducing time complexity. By reusing computed results, they can significantly improve the efficiency of algorithms.

3. **Differences**:

   - **Top-Down vs. Bottom-Up**: Memoization is a top-down approach, where you start with the original problem and break it down into subproblems through recursion. Dynamic programming often uses a bottom-up approach, where you start with the simplest subproblems and build up to solve the larger problem.

   - **Storage**: Memoization typically uses data structures like dictionaries or hash tables to store previously computed results for specific input values. Dynamic programming often uses arrays or matrices to store results for subproblems.

   - **Control Flow**: In memoization, control flow is typically guided by recursive function calls. Dynamic programming often uses loops to iterate through subproblems systematically.

In summary, memoization is a specific technique within the broader field of dynamic programming. Both approaches share the fundamental idea of breaking down complex problems into smaller subproblems and reusing solutions to optimize algorithms. The choice between memoization and bottom-up dynamic programming often depends on the problem and programming preferences, with both techniques offering powerful tools for optimization.