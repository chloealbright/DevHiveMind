---
tags:
  - looping
  - traversal
  - search
  - linear
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates: "[[Iterating vs Traversing]]"
---
![[unnamed (59).gif]]


## Linear iteration

Linear iteration is a broader concept that refers to the process of sequentially visiting or processing each item in a collection/Data Structure, typically from the first item to the last, in a linear order.  It is not limited to searching for a specific value like a [[Linear search vs Binary search#^d39416 | Linear Search]]; it can involve various operations on each item in the collection, such as printing, modification, or computation.  

```javascript
function linearIteration(arr) {
  for (let index = 0; index < arr.length; index++) {
    // Process the element at the current index
    console.log(arr[index]);
  }
}

const myArray = [1, 2, 3, 4, 5];
linearIteration(myArray);
```

## Linear Recursion

While it's not a common approach, you can implement linear iteration using recursion. Here's an example of how you can do this by creating a recursive function to iterate over an array of elements and process each element one by one:  
  
```javascript  
function linearIterationRecursive(arr, index) {  
// Base case: When the index is equal to the length of the array, stop the recursion.  
if (index === arr.length) {  
return;  
}  
  
// Process the element at the current index  
console.log(arr[index]);  
  
// Recursive call to process the next element  
linearIterationRecursive(arr, index + 1);  
}  
  
const myArray = [1, 2, 3, 4, 5];  
linearIterationRecursive(myArray, 0);  
```  
  
In this example, the `linearIterationRecursive` function takes an array `arr` and an `index` as parameters. It processes the element at the current index and then makes a recursive call to process the next element by incrementing the index. The base case checks if the index is equal to the length of the array, and if so, it stops the recursion.  
  
It's important to note that while this code demonstrates a recursive approach for linear iteration, it's not the most efficient or common way to achieve linear iteration. Using a "for" loop is a more straightforward and efficient choice for linear iteration in most cases.

## Binary Iteration

```javascript
const searchIter = (nums, target) => {
    let lo = 0;
    let hi = nums.length - 1;
    while (lo <= hi) {
        let mid = lo + Math.floor((hi - lo + 1) / 2);
        if (target < nums[mid]) {
            hi = mid - 1; // index
        } else {
            lo = mid; // index
        }
    }
    return nums[lo] == target ? lo : -1;
};

```


## Binary Recursion

```javascript
const searchRec = (nums, target) => {
    return findTarget(nums, target, 0, nums.length - 1);
};

const findTarget = (nums, target, start, end) => {
    if (start > end) {
        return -1;
    }
    const mid = Math.floor((end - start) / 2) + start;
    if (nums[mid] == target) {
        return mid;
    } else if (nums[mid] > target) {
        return findTarget(nums, target, start, mid - 1); // Adjust the end index to mid - 1
    } else {
        return findTarget(nums, target, mid + 1, end); // Adjust the start index to mid + 1
    }
};

```




## More Recursive & Iterative Code Examples
### Array

```javascript
function ArrayIterative (arr){  

  for (let i = 0; i < arr.length; i++) {  
     console.log( arr[i])  
}  

}     
```

```javascript
function ArrayRecursive(arr, index=0) {  

if (arr.length === index) {  
return;  

}  

console.log(arr[index])  

ArrayRecursive(arr, ++index)  
}  
```


### 2D Array


```javascript
function matrixIter(array) {  

for(let row = 0; row < array.length; row++){  

   for(let col = 0; col < array[row].length; col++) {  

       console.log(array[row][col]);  

          }  
 }     

}  
```

```javascript
 function recursiveMatrixTraversal(matrix: number[][], row: number, col: number, action: (value: number) => void) {
  // Check if the row and column are within valid bounds
  if (
    row < 0 ||
    col < 0 ||
    row >= matrix.length ||
    col >= matrix[0].length
  ) {
    return;
  }

  // Perform the action on the current cell
  action(matrix[row][col]);

  // Recursively traverse in all four directions: up, down, left, right
  recursiveMatrixTraversal(matrix, row - 1, col, action); // Up
  recursiveMatrixTraversal(matrix, row + 1, col, action); // Down
  recursiveMatrixTraversal(matrix, row, col - 1, action); // Left
  recursiveMatrixTraversal(matrix, row, col + 1, action); // Right
}

// Example usage:
const matrix: number[][] = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

// Define an action to perform on each cell (e.g., printing the value)
function printValue(value: number) {
  console.log(`Visited cell with value: ${value}`);
}

// Start traversal from a specific cell (e.g., top-left corner)
recursiveMatrixTraversal(matrix, 0, 0, printValue);
```

### Linked List

```javascript
function printFoward(node) {  

let current = node;  

while(current!== null){  

 console.log(current.value)  

 current = current.next  // equvivalent to i++ in a loop  

}  

}  

function printFowardRec(node){  

let current = node;  

if(current!== null){  

   console.log(current.value)  

   current = printFowardRec(current.next)    
 }  
}  
```

```javascript
function reverseListIter(head) {  

if (!head) return null;  

let current = head;  

let previous = null;  

while (current !== null) {  

let next = current.next;  

current.next = previous;   
previous = current;   
current = next;   

}  

return previous;  

};  


function reverseListRec(head, prev = null) {  

if (!head) return prev;  

let current = head;  
let next = current.next;   

current.next = prev;       
prev = current;         

return reverseListRec(next, prev)  

};  
```


### Tree BFS Using Queue Implemented with Linked List

```javascript
function breadthFirstSearch(root) {
  if (!root) return [];

  const result = [];
  const queue = [root];

  while (queue.length) {
    const node = queue.shift();
    result.push(node.value);

    if (node.left) queue.push(node.left);
    if (node.right) queue.push(node.right);
  }

  return result;
}
```


### Tree DFS(Pre/In/Post) Order Using Stack 
 # Implemented with Array or Linked List

```javascript    
function IterativePreOrder(){  

let stack = [root]  
let res = []  

 
while (stack.length) {        

let curr = stack.pop()  

res.push(curr.key)  

if (curr.left) stack.push(curr.left)  


if (curr.right) stack.push(curr.right)  
  

}  

return res.reverse()  

 
}  


function recursivePreOrder(root) {
  if (!root) {
    return [];
  }

  const result = [];

  function traverse(node) {
    if (node) {
      result.push(node.key); // Process the current node
      traverse(node.left);    // Recursively traverse the left subtree
      traverse(node.right);   // Recursively traverse the right subtree
    }
  }

  traverse(root);

  return result;
}


```

```javascript


function IterativeInOrder(){  

let stack = [root]  
let res = []  

while (stack.length) {        

if (curr.left) stack.push(curr.left)  

let curr = stack.pop()  

res.push(curr.key)  

if (curr.right) stack.push(curr.right)  }  

return res.reverse()  

}  

function recursiveInOrder(root) {
  if (!root) {
    return [];
  }

  const result = [];

  function traverse(node) {
    if (node) {
      traverse(node.left);    // Recursively traverse the left subtree
      result.push(node.key);  // Process the current node
      traverse(node.right);   // Recursively traverse the right subtree
    }
  }

  traverse(root);

  return result;
}


```

```javascript
    

function IterativePostOrder(){  

let stack = [root]  
let res = []  

while (stack.length) {        

if (curr.left) stack.push(curr.left)  
if (curr.right) stack.push(curr.right)  

let curr = stack.pop()  

res.push(curr.key)  

}  

return res.reverse()  

}     


function recursivePostOrder(root) {
  if (!root) {
    return [];
  }

  const result = [];

  function traverse(node) {
    if (node) {
      traverse(node.left);    // Recursively traverse the left subtree
      traverse(node.right);   // Recursively traverse the right subtree
      result.push(node.key);  // Process the current node
    }
  }

  traverse(root);

  return result;
}


```




### Graph BFS

```javascript
function breadthFirstSearch(startVertex, graph) {
  const visited = new Set();
  const queue = [startVertex];
  const result = [];

  visited.add(startVertex);

  while (queue.length > 0) {
    const currentVertex = queue.shift();
    result.push(currentVertex);

    for (const neighbor of graph[currentVertex]) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        queue.push(neighbor);
      }
    }
  }

  return result;
}

// Example usage:
const graph = {
  A: ['B', 'C'],
  B: ['A', 'D'],
  C: ['A', 'E'],
  D: ['B', 'E'],
  E: ['C', 'D'],
};

const bfsResult = breadthFirstSearch('A', graph);
console.log(bfsResult); // Output: ['A', 'B', 'C', 'D', 'E']
```


```javascript
function recursiveBFS(startVertex, graph) {
  const visited = new Set();
  const queue = [startVertex];

  function visitNeighbors(node) {
    if (node === null || visited.has(node)) {
      return;
    }
    visited.add(node);
    console.log(node); // Process the current node

    for (const neighbor of graph[node]) {
      if (!visited.has(neighbor)) {
        queue.push(neighbor);
      }
    }
    if (queue.length > 0) {
      visitNeighbors(queue.shift());
    }
  }

  visitNeighbors(startVertex);
}

// Example usage:
const graph = {
  A: ['B', 'C'],
  B: ['A', 'D'],
  C: ['A', 'E'],
  D: ['B', 'E'],
  E: ['C', 'D'],
};

console.log("BFS Traversal:");
recursiveBFS('A', graph);
```

### Graph DFS
>[!important] 
>In graph DFS, the concept of "in-order" doesn't apply in the same way because there may not be a strict hierarchy or ordering between neighbors.

```javascript
function iterativeDFSPreOrder(graph, startNode) {
  const visited = new Set();
  const stack = [startNode];
  const result = [];

  while (stack.length) {
    const currentNode = stack.pop();
    if (!visited.has(currentNode)) {
      result.push(currentNode); // Pre-order processing
      visited.add(currentNode);

      for (const neighbor of graph[currentNode]) {
        if (!visited.has(neighbor)) {
          stack.push(neighbor);
        }
      }
    }
  }

  return result;
}


function recursiveDFSPreOrder(graph, currentNode, visited = new Set(), result = []) {
  if (!visited.has(currentNode)) {
    result.push(currentNode); // Pre-order processing
    visited.add(currentNode);

    for (const neighbor of graph[currentNode]) {
      if (!visited.has(neighbor)) {
        recursiveDFSPreOrder(graph, neighbor, visited, result);
      }
    }
  }

  return result;
}
```


```javascript
function iterativeDFSPostOrder(graph, startNode) {
  const visited = new Set();
  const stack = [startNode];
  const result = [];

  while (stack.length) {
    const currentNode = stack[stack.length - 1];

    if (visited.has(currentNode)) {
      stack.pop();
      result.push(currentNode); // Post-order processing
    } else {
      visited.add(currentNode);

      for (const neighbor of graph[currentNode]) {
        if (!visited.has(neighbor)) {
          stack.push(neighbor);
        }
      }
    }
  }

  return result;
}


function recursiveDFSPostOrder(graph, currentNode, visited = new Set(), result = []) {
  if (!visited.has(currentNode)) {
    visited.add(currentNode);

    for (const neighbor of graph[currentNode]) {
      if (!visited.has(neighbor)) {
        recursiveDFSPostOrder(graph, neighbor, visited, result);
      }
    }

    result.push(currentNode); // Post-order processing
  }

  return result;
}
```

