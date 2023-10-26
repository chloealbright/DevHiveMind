---
tags:
  - bfs
  - dfs
  - AlgorithmExamination
  - potentialMerge
  - search
  - looping
  - traversal
author: jacgit18
---
**The essence of DFS and BFS lies in the order of operations and base cases, depending on the specific problem.**

## **Breadth-First Search (BFS) with Queue (Applicable to Trees and Graphs) - O(|V|)**

### Tree

1. Store the `[tree]` in a queue with an initial length of 1.
2. Initialize a `currentNode` variable.
3. Create an empty `result` array to store the results.
4. Iterate while the queue length is greater than 0.
5. Assign `currentNode` by shifting from the queue, which removes the root node from the queue.
6. Check the left and right children of the current node and add their references to the queue.
7. Push 12 to the result array.
8. Repeat the process by shifting out the left child, which leaves only the right child in the queue. Focus on the current node, which contains the left child. Add its children to the queue and repeat until the queue is empty.

### Graph

1. Create and store the graph in a queue.
2. Initialize a `current` variable.
3. Create and store the added graph nodes in a new set.
4. Loop through the queue while its length is greater than 0.
5. Update `current` by dequeuing (using `queue.shift()`) the first element from the queue.
6. Loop through the edges of the graph, checking if they have been visited with the set.
7. Push and add the edge into the queue and set.
8. Perform any desired action with `current.id`, such as pushing it to an array.

## **Depth-First Search (DFS) with Stack (Applicable to Trees and Graphs) - O(|V|)**

For DFS, it's not about the queue but more about the order of traversal.

### Tree

**Tree Preorder:**

```javascript
BASE CASE
Action
Left Check = Recursive call with node.left as the parameter
Right Check = Recursive call with node.right as the parameter
```

**Tree Inorder:**

```javascript
BASE CASE
Left Check = Recursive call with node.left as the parameter
Action
Right Check = Recursive call with node.right as the parameter
```

**Tree Postorder:**

```javascript
BASE CASE
if (node == null) return 0; // Alternative cases
Left Check = Recursive call with node.left as the parameter
Right Check = Recursive call with node.right as the parameter
Action Example: Get the height - `return Math.max(left, right) + 1;`
Alternative action: Push the current node to a value array
```

### Graph

**Graph DFS (No Pre/In/Post Order):**

It's similar to BFS but uses stacks with `pop()` instead of `shift()`. The order of operations in recursive implementation might mimic pre and post-order traversal, even though these concepts may not directly apply to graphs.

1. Create and store the graph in a stack.
2. Initialize a `current` variable.
3. Create and store the added graph nodes in a new set.
4. Loop through the stack while its length is greater than 0.
5. Update `current` by popping (using `stack.pop()`) the last element from the stack.
6. Loop through the edges of the graph, checking if they have been visited with the set.
7. Push and add the edge into the stack and set.
8. Perform any desired action with `current.id`, such as pushing it to an array.

```
 * 

 *                     2 

 *                   /   \ 

 *            0 ~~~ 1    4  ~~~ 5 ~~~ 3 

 *                \   / \    / 

 *                  7     6 

DFS: [ 

  0, 

  1, 7, 4, 

  6, 5, 3, 

  2 

] 
```
## **Topological Sort (Graphs)**

To be added.

## **Dynamic Programming with Memoization**

### K-way/2-way Merge (Dynamic Programming)

Dealing with multiple arrays, rows in two-dimensional arrays, or multiple linked lists, where you find the lowest value and store them in order from least to greatest, similar to a min-heap or merge sort.

### Knapsack (Dynamic Programming)

To be added.

### Memoization

Memoization is akin to caching and can be used with closures. Before returning a function to be called, you create an empty cache object. When you call the function, you store the return value in a variable. When checking if a value is in the cache, return it if it exists; otherwise, update the cache and return the value, which can be a variable, a recursive call, or a function call.

### Top-Down vs. Bottom-Up

- **Top-Down**: Starts from a bigger, more abstract picture and works towards smaller details. It's recursive and can exceed the call stack with large values. Memoization is recommended for pure functions where inputs result in predictable outputs.

- **Bottom-Up (Tabulation)**: Is iterative and often faster, especially with large values. It's data-driven and uses known information to compute unknown values. It follows a different approach where you first address unknown indices and then use known values to fill in the gaps.

For more information on dynamic programming patterns, you can refer to this [resource](https://mageswaran1989.medium.com/a-mind-map-of-dynamic-programming-patterns-to-ace-interviews-72ff0370bb27).
