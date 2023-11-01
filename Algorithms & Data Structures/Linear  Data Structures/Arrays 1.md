---
tags:
  - linear
author: jacgit18
Status: init
Started: 
EditDate: 
Relates:
---


An array is a linear data structure that allows sequential access. It can be thought of as a special object, representing a chunk of memory.

Arrays in different programming languages can take different forms, such as object literals or key-value pairs.

Here are some examples in Java and TypeScript:

```java
ArrayList<Object> x = new ArrayList<Object>();
ArrayList[][] = new ArrayList();
```

```typescript
let v: string = new Array();
let a: [][] = new Array<Array<Object>>();
```

Use arrays for pushing, popping, and looking up data because these operations are typically O(1) and ordered.

Avoid using arrays for inserting or deleting data, as these operations are O(n). Depending on the language, arrays can be static, meaning they have a fixed size, and making them dynamic can result in O(n) or worse time complexity.

Array sizes are often hardcoded, making them inflexible in terms of dynamic resizing. To resize an array, you usually have to copy it to new memory with a different array size, which is inefficient in terms of steps.

Arrays are fast due to their indexing, especially when performing binary searches and sorting.

Arrays and strings share similarities, as they both have sub-arrays and sub-strings. You can use array brackets to iterate and apply other string methods.

When working with strings, consider whether they are ASCII or Unicode strings. This distinction can be important for certain tasks.

JavaScript does not natively provide multidimensional arrays, but you can create them by defining an array of elements, where each element is itself another array.

Tip: When working with nested arrays and you don't need to visit all indexes, use a single loop instead of nested loops for improved efficiency.

It's essential to use the right data structure for your needs. In Java, ArrayLists are more dynamic and can grow, unlike regular arrays with fixed sizes.

When working with arrays, consider using map over the forEach method for better functionality.

If you need to reverse or limit elements in an array, consider using the .sort method.

For questions involving nested arrays or matrices, think about working with the outer row loop and consider using a hash table to track visited elements, similar to memoization.

If you have an array with fixed-length elements, you might encounter scenarios like merging intervals where values are either unsorted or sorted.

Additionally, you can use the spread operator to manipulate strings and store the result in an array for array destructuring.

To shrink an array, you can reassign its length to a smaller value.

Sorting an array by the length of its elements is possible for more complex data structures.

Lastly, you can use optional chaining and the null coalescing operator to handle cases where arrays may not exist or their length is unknown.

I hope these refinements help improve the clarity and accuracy of your note about arrays. If you have any specific questions or need further improvements, please let me know.