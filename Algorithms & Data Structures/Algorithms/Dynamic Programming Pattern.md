---
tags: []
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
## Memoization and Dynamic Programming

>[!note] Probably will come up with FANG Companies
### Understanding Caching

- **Caching** is a technique used to store values for future use, reducing the need for recomputation.
- Think of caching as having a backpack where you keep frequently used items for quick access, similar to reusing books or a pencil for school.


>[!important] 
> Divide&Conquer(includes Recursion) + memoization = Dynamic programming  

### Memoization

- **Memoization** is a form of caching often used in **dynamic programming**.
- It involves storing the return values of a function based on its parameters to avoid redundant calculations.
- Ideal for problems with repetitive subproblems.

#### Implementing Memoization

```javascript
export const memoize = (fn) => {
  const cache = {};

  return (...args) => {
    const key = JSON.stringify(args);

    if (key in cache) {
      return cache[key];
    }

    const result = fn(...args);
    cache[key] = result;
    return result;
  };
};
```

### Dynamic Programming

- **Dynamic programming** is an optimization technique.
- It involves breaking down a problem into subproblems, solving each subproblem only once, and storing their solutions.
- Great for problems with overlapping subproblems.

#### How to Determine If Dynamic Programming Is Suitable

1. **Divide into Subproblems**:
   - Can the problem be divided into smaller subproblems?
   - Recursive solutions often indicate a potential for dynamic programming.

2. **Repetitive Subproblems**:
   - Are the subproblems repetitive, i.e., the same calculations occur multiple times?
   - If yes, you can apply memoization to store and reuse solutions.

>[!note]  Dynamic Programming Flow
Divide into sub-Problems -> solve with recursion -> memioze or tabulate subproblems and store  
### Top-Down vs. Bottom-Up

- **Top-Down Approach** (***Memoization***):
  - Recursive approach.
  - Suitable for smaller input values.
  - Useful for functions where inputs predictably lead to the same outputs.


- **Bottom-Up Approach** (***Tabulation***):
  - Iterative and often more efficient, especially for large values.
  - Uses known information to compute unknown values.
  - Best for large-scale problems.

#### Example: Fibonacci Sequence

- **Top-Down Approach**:
  - Uses closure, recursion, and memoization.
  - Suitable for shallow trees with small input values.

```javascript
function fibonacciMaster() { // O(n)
  let cache = {};
  return function fib(n) {
    calculations++;
    if (n in cache) {
      return cache[n];
    } else {
      if (n < 2) {
        return n;
      } else {
        cache[n] = fib(n - 1) + fib(n - 2);
        return cache[n];
      }
    }
  }
}
```

- **Bottom-Up Approach**:
  - An iterative approach.
  - More efficient for large values or deeper trees.


```javascript
function fibonacciMaster2(n) { 

  let answer = [0,1]; 

  for ( let i = 2; i <= n; i++) { 

    answer.push(answer[i-2]+ answer[i-1]); 

  } 

  return answer.pop(); 

} 
```

### Benefits of Memoization and Dynamic Programming

- Save computation time by reusing results.
- Optimize performance in various fields of computer science.
- An effective tool for algorithm optimization.



  
