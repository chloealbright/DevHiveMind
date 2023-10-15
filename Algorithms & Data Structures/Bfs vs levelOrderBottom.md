Bfs Basic with queue vs levelOrderBottom with pure Recursion

The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.  
  
// similar to dfs post order but uses queues  
function bfs(node) {  
let queue = [node];  
let current;  
let result = [];  
  
while(queue.length>0) {  
current = queue.shift();// rm and stores first node val  
  
if(current.left !== null) queue.push(current.left);  
  
if(current.right !== null) queue.push(current.right);  
  
result.push(current.value);  
  
}  
  
  
return result;  
}  
  
VS  
  
  
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