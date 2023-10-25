---
tags:
  - AlgorithmExamination
author: jacgit18
---
**BFS with Queue:**
```javascript
function bfs(node) {
  let queue = [node];
  let current;
  let result = [];

  while (queue.length > 0) {
    current = queue.shift(); // Remove and store the first node's value

    if (current.left !== null) queue.push(current.left);
    if (current.right !== null) queue.push(current.right);

    result.push(current.value);
  }

  return result;
}
```
The `shift()` method removes the first element from an array and returns that removed element. This method changes the length of the array.  


**Level Order with Pure Recursion:**
```javascript
var levelOrderBottom = function(root) {
  if (root == null) {
    return root;
  }
  let h = maxHeight(root);
  let results = [];
  let depth = 1;
  
  for (depth; depth <= h; depth++) {
    results.push(levelOrder(root, depth));
  }

  // You can return the results in reverse order if needed.
  // return results.reverse();
  return results;
};

function levelOrder(node, d, level = []) {
  if (node == null) {
    return level;
  }
  if (d === 1) {
    level.push(node.value);
  } else if (d > 1) {
    levelOrder(node.left, d - 1, level);
    levelOrder(node.right, d - 1, level);
  }
  return level;
}
```

Here's a brief comparison between the two methods:

- **BFS with Queue**: This method uses a queue data structure to perform a breadth-first traversal of the tree. It iterates through the nodes level by level. This approach is more straightforward and efficient in terms of space complexity because it uses an external data structure (the queue) to manage the traversal.

- **Level Order with Pure Recursion**: This method uses pure recursion to traverse the tree level by level. It calculates the maximum height of the tree and then recursively extracts values at each level. It's less efficient in terms of space complexity because it uses the call stack for recursion, which may lead to stack overflow errors for very deep trees.

Depending on your specific use case and performance requirements, you can choose the method that best suits your needs. The BFS with a queue is often preferred for its simplicity and space efficiency, while the pure recursion method might be useful for educational or conceptual purposes but may have limitations in practical applications.