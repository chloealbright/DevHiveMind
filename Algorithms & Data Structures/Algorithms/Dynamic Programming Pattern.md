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

### Memoization inDepth




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








  
