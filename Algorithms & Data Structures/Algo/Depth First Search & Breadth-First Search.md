---
tags:
  - bfs
  - dfs
  - AlgorithmExamination
  - potentialMerge
  - looping
  - search
  - traversal
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (43).gif]]

**The essence of DFS and BFS lies in the order of operations and base cases, depending on the specific problem.**

**DFS (Depth-First Search):**

DFS is an algorithm designed for traversing or searching tree data structures. It begins at the root node and explores as deeply as possible along each branch before backtracking. In simpler terms, DFS explores a path all the way to a leaf before considering another path.

**BFS (Breadth-First Search):**

BFS, on the other hand, is another algorithm for traversing or searching tree data structures. It starts at the root node and initially explores the neighbor nodes before moving to the next level neighbors. This approach ensures that BFS traverses the tree level by level and depth by depth.

It's important to note that the choice between DFS and BFS depends on the problem at hand. BFS is ideal when searching for something closer to the root, while DFS is more suitable when the target node is closer to a leaf.

The choice of data structures for these algorithms is crucial:

- BFS traditionally employs a queue, as it processes nodes in a first-in-first-out manner.
- DFS can be implemented with a stack, and whether you choose a linked list or an array depends on your specific requirements. Arrays are faster but less dynamic.

#### Here's a quick reference to the data structures for each algorithm:

**For BFS (Queue ***implemented with Linked List***):**
- Use `enqueue()` to add elements to the end of the queue implemented by linked list vs if implemented by array you would  `push()`.  
- Use `dequeue()` to remove elements from the front of the queue. You can build these functions as needed for a linked list-based queue vs the array implementation uses `pop()`


**For DFS (Stack with array is simpler):**
> *If you use linked list implemented stack it,s good to use if you anticipate a lot of adding and removing of elements
- Use `pop()` (removes the last element) - Standard for stacks.
- Use `push()` - Typical for stacks.


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
