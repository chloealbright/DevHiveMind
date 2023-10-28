---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Creating root  with new instance Tree node with a key value value and that gets stored in TreeNode Class then crate a new instances referring to the original root instance to assign left and right values  

class TreeNode { 

  constructor(value) { 

    this.value = value; 

    this.left = null; 

    this.right = null; 

  } 

}; 

let root = new TreeNode(12); 

root.left = new TreeNode(7); 

root.left.left = new TreeNode(9); 

root.left.left.left = new TreeNode(0); 

root.right = new TreeNode(1); 

root.right.left = new TreeNode(10); 

root.right.right = new TreeNode(5); 

function height(node) { 

  if (node == null) { 

    /* base case */ 

    return 0; 

  } 

 // let left = height(node.left); 

 // let right = height(node.right); 

return Math.max(height(node.left), height(node.right)) + 1 

//returns min 

//return Math.min(height(node.left), height(node.right)) + 1 

 // return Math.max(left, right) + 1; returns once let and right are checked 

} 

console.log(height(root) ) 

let Height =  height(root) returns 4 

we check all the lefts until check last left which is null so we we check right which is null so pop off call stack adding 1 to the left since we checked both sides on the deepest left and continue the last call stack frame meaning we go back  to the parent node and check it right then we add 1 again to the left 

max check highest value between left and right initially returns 0  then we add 1 to that value since we checked left and right and count is return to the parent node which is left so left count is 1 then we repeat process until we reach root left were the count is 3 and check root right side 

at end when we check root left and right count left is 3 and right is 2 so left is higher and 1 is added thus we return 4 and that extra 1 represents the left node right had 

the right of the left since null we return then we return from the 

[https://adrianmejia.com/data-structures-for-beginners-trees-binary-search-tree-tutorial/](https://adrianmejia.com/data-structures-for-beginners-trees-binary-search-tree-tutorial/)



Figure out were to put 


Tree 

May have multiple nodes or Trees 

Create/Store dummy node which can be used depends on scenario  

Iterate through one or more list so                                                             

while  stack.length  or  queue.length > 0      

  if current !== null do something then increment                                

  current= current.next EDIT 




tree sideWays bfs count  

Use .map() when you want to create a new array of transformed values of the original array or other data Structures by iterating over and calling a function on every element of said original array. Use a for loop when you need a less specialized and more flexible iterator. 

when dealing with 2 values  

use bfs algo and count var 

and depending where your are on tree 

add decremented or incremented count to map with current  node values







Symmetric SubTree Attributes Traverse level by level outer nodes then inner nodes LC 101 

check if tree is null  if (root == null) return true; 

Return helper method call with params of root.left and root.right that is recursive 

Check Properties of tree symmetry  

	check tree left && right node properties if they are both null return true or alt value depending on what goal is in the code 

	check if  left || right node of tree property is null return false or alt value depending on what goal is in the code 

	check  left and right node properties value if they aren't equal to each other return false or alt value depending on what goal is in the code 

return  2 recursive calls  

Call 1 takes in param of left.left for outer left node checks and right.right for outer right node checks  

&& 

Call 2 takes in param of left.right for inner nodes of left and right.left for inner nodes of right




