---
tags:
  - bfs
  - dfs
  - looping
  - traversal
  - search
  - potentialMerge
  - binary
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[fusion.gif]]



trees and graphs are kind of binary by nature so non linear



Linear search algorithm is a set of sequential instructions to traverse one by one(Brute Force) starting from the beginning of an array or whatever linear data structure you iterate through and is linear in runtime complexity and is good for searching through small data sets.   

LINEAR O(N) 
```javascript
function indexEqualsValueSearch(arr) { 

  let low = 0 

  let high = arr.length  

  let mid = arr.length / 2; 

  let min = Infinity; 

    for(let start = 0; start < high; ++start )  { 

      if(arr[start] === start){ 

        min = Math.min(min, arr[start] ) 

      } 

    } 

  return min === Infinity ? -1 : min 

 // check current index and  value to see if they match  and find lowest match min 

} 



// ITERATION vs RECURSION core difference is checking left or right and some sub action when check is true vs base case and just doing recursive call where you pass in left or right with know check or a check depending on the context  

// Ex: iter is if (curr.left) stack.push(curr.left) vs rec is recPreOrder(root.left);  

```

```javascript
function ArrayIterative (arr){  

  for (let i = 0; i < arr.length; i++) {  
     console.log( arr[i])  
}  

}  

      

function ArrayRecursive(arr, index=0) {  

if (arr.length === index) {  
return;  

}  

console.log(arr[index])  

ArrayRecursive(arr, ++index)  

}  


```


```javascript
function matrixIter(array) {  

for(let row = 0; row < array.length; row++){  

   for(let col = 0; col < array[row].length; col++) {  

       console.log(array[row][col]);  

          }  
 }     

}  


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


```javascript    
TREE ITERATION      
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
```



```javascript
TREE RECURSION DFS 
function recPreOrder(root){  

let resultPre = []  


if (root === null) return;   

resultPre.push(root.value); //A  
recPreOrder(root.left); //L  
recPreOrder(root.right); //R  

return resultPre;  

}  

    

function recInOrder(root){  

let resultIn = []  
if (root === null) return;   

recInOrder(root.left); //L  
resultIn.push(root.value); //A  
recInOrder(root.right); //R  

return resultIn;  

}  

    

function recPostOrder(root){  

let resultPost = []  

if (root === null) return;   

recPostOrder(root.left); //L  
recPostOrder(root.right); //R  
resultPost.push(root.value); //A  

return resultPost;  

}  
      
```

```javascript
// Graph  
function dfsIterative(vertex) {  

let result = [];  
let stack = [vertex];  
let current;  
let visited = new Set();  

visited.add(vertex);  

while (stack.length > 0) {  

 current = stack.pop();  

   for (const edge of current.edges){  

   if (!visited.has(edge)) {  

     stack.push(edge);  
     visited.add(edge);  


         }  
 }  

 result.push(current.id);  


}  

return result;  

}  

      

function dfsRecursive(vertex) {  

let result = [];  
let visited = new Set();  


function helper(current) {  

if(visited.has(current)) return;  


visited.add(current); 
result.push(current.id);  

 for (let edge of current.edges){  

   helper(edge)  

 }  

}   

helper(vertex)  

return result;  


}  

```



```javascript
function bfs(node) {  

let queue = [node];  
let current;  
let result = [];  
 

while(queue.length>0) {  

 current = queue.shift();  

 if(current.left !== null)  queue.push(current.left);  
 if(current.right !== null)  queue.push(current.right);  

 result.push(current.value);  

}  

return result;  

}  
```




```javascript
function bfs(vertex) {  

let result = [];  
let queue = [vertex];   
let current;  
let visited = new Set();  

visited.add(vertex); // the whole graph is stored so set is of size 1  


while (queue.length > 0) {  

 current = queue.shift();  

for (const edge of current.edges){  

if (!visited.has(edge)) {  

 queue.push(edge); 
 visited.add(edge);  
}  

}  

 result. push(current.id);  

}  

return result;  

}

```




Certainly! Here are the recursive BFS implementations for both a tree and a graph in JavaScript:

**Recursive BFS on a Tree:**

```javascript
class TreeNode {
    constructor(value) {
        this.value = value;
        this.children = [];
    }
}

function recursiveBFSInTree(node) {
    if (!node) {
        return;
    }
    
    const queue = [node];
    
    while (queue.length > 0) {
        const current = queue.shift();
        console.log(current.value);
        queue.push(...current.children);
    }
}

// Example usage
const root = new TreeNode(1);
root.children.push(new TreeNode(2), new TreeNode(3));
root.children[0].children.push(new TreeNode(4), new TreeNode(5));
root.children[1].children.push(new TreeNode(6), new TreeNode(7));

recursiveBFSInTree(root);
```

**Recursive BFS on a Graph:**

```javascript
class Graph {
    constructor() {
        this.graph = {};
    }

    addEdge(node, neighbor) {
        if (!this.graph[node]) {
            this.graph[node] = [];
        }
        this.graph[node].push(neighbor);
    }
}

function recursiveBFSInGraph(graph, node, visited = new Set()) {
    if (!visited.has(node)) {
        console.log(node);
        visited.add(node);
        const neighbors = graph[node] || [];
        for (const neighbor of neighbors) {
            recursiveBFSInGraph(graph, neighbor, visited);
        }
    }
}

// Example usage
const g = new Graph();
g.addEdge(0, 1);
g.addEdge(0, 2);
g.addEdge(1, 2);
g.addEdge(2, 0);
g.addEdge(2, 3);
g.addEdge(3, 3);

recursiveBFSInGraph(g.graph, 2);
```

These JavaScript examples provide recursive BFS implementations for both trees and graphs, demonstrating how the logic can be applied in a recursive manner.