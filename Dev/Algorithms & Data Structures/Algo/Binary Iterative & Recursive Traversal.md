![](_Files/Algo/fusion.gif)

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

      


function matrixIter(array) {  

for(let row = 0; row < array.length; row++){  

   for(let col = 0; col < array[row].length; col++) {  

       console.log(array[row][col]);  

          }  
 }     

}  


    

// SLIGHT FIX NEEDED  
function matrixRecursion(arr, currRow = 0, currCol = 0) {  

let columnBoundary = currCol === arr.length +1;  

if (columnBoundary) return 0;  
let rowBound = currRow >=  arr.length;  
 
if (rowBound) return 1;  

//rm undefined since column check shows undefined  

if(arr[currRow][currCol] !== undefined){  

   console.log(arr[currRow][currCol]);  

}  

   
// Recursive call to traverse the matrix  

// in the Horizontal direction  

if (matrixRecursion(arr, currRow, currCol + 1) === 1) return 1;  

return matrixRecursion(arr, currRow + 1, 0);  

}  

  

traverseMatrix(arr) // weird behavior with let arr = [ [ 1, 2, 3 ] ]; prints up to 2  


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

      

TREE RECURSION  
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

          

Graph  
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