The core of DFS and BFS isn't the queue or stack it is the order of operation and base cases depending on the question 

## **BFQueueS**(Apply to Tree & Graph)O(|V|) 

## Tree 

Store [tree] in queue // the length is 1 

initialize currentNode variable 

initialize empty result array to push to 

iterate through queue length while its greater then 0 

resign  currentNode to queue.shift() which rm root and stores if in currentNode 

check root left and right and push it,s reference into memory inside queue 

then push 12 to result  then repeat we shift out the left we stored which leaves us with only right in the queue but we put all are focus on the current which contains the left we shift and take a look at its children which get added to queue and we repeat the process till queues is empty  

## Graph 

Create/Store graph in queue  

Create current  

Create/Store add graph into new set  

loop through length of queue as long as greeter then 0 

Update current to first element removed by queue.shift()   

loop through graph edges array checking if we visited with set 

then pushing and adding edge into queue and set  

then do whatever action you want with current.id like pushing it to an array 

## **DFStack**(Apply to Tree & Graph) O(|V|) more so the order not the queue is the core just in terms of traversal 

## Tree 

TREE PRE ORDER:  

```javascript
BASE CASE 

Action 

left Check = Recursivecall with node.left param  

right Check = Recursivecall with node.right param  
```

 TREE INORDER:  

```javascript
BASE CASE 

left Check = Recursivecall with node.left param  

action 

right Check = Recursivecall with node.right param  
```

TREE POST ORDER:  

```javascript
BASE CASE 

 if (node == null) return 0; alt cases 

left Check = Recursivecall with node.left param  

right Check = Recursivecall with node.right param  

action Example get height  return Math.max(left, right) + 1; 

alt action Push current node to value array 
```

Graph DFS - (NO PRE/IN/POST ORDER):  is basically BFS but with stacks and pop() instead of shift were we update the current but if doing recursive Implementation the way recursion works if you move the (recursive call or maybe the operating you perform with set it almost acts as a PRE & POST order even though for graphs that doesn't apply because the way it is structured and the set being used) 

```javascript
Create/Store graph in stack 

Create current  

Create/Store add graph into new set  

loop through length of stack as long as greeter then 0 

Update current to last element removed by stack.pop()   

loop through graph edges array checking if we visited with set 

then pushing and adding edge into stack and set  

then do whatever action you want with current.id like pushing it to an array 
```

```
 * 

 *                     2 

 *                   /   \ 

 *            0 ~~~ 1    4  ~~~ 5 ~~~ 3 

 *                  \   / \    / 

 *                    7     6 

DFS: [ 

  0, 

  1, 7, 4, 

  6, 5, 3, 

  2 

] 
```
## Topological Sort (Graphs) 

todo 

## Dynamic Programming can involve memoize  

### K-way/2-way - Merge (Dynamic Programming) 

Dealing with multiple arrays or rows in two dimensional arrays or multiple linked list or other data structures were your finding lowest value and storing them somewhere in order from least to greatest kind of like a min heap or merge sort a little 

### Knapsack (Dynamic Programming) 

todo 

### Memoize is basically caching can be used with closure were we create empty cache object before return function to call you create a variable to store function return then call variable with param value 

```
check if a cache has param if does return current param in cache[n] 

else update cache[n] with param =  which can be a variable or Recursive call or function call  
```

### Top Down starts from bigger abstract picture  to smaller detailed picture 

	Top Down  is recursive so you can exceed call stack with large values so you want to implement Memiozation also Memiozation should only be used for pure functions since your taken in a predictable input and getting a predictable output but you getting memory but for the cost of speed but good for tree like question were work is being repeated 

### Bottom up is iterative and is more faster especially with large values and is data driven and is known Tabulation 

	basically use known info like the first two index of a array to get other values in the array 

	there is also a dynamic way of doing it by going after unknown index then get known  it's like following a path from different points essentially  

Example top down is like reading a paper from top to  bottom while bottom up is like starting at the middle then end then beginning to get an idea of the bigger picture 

[https://mageswaran1989.medium.com/a-mind-map-of-dynamic-programming-patterns-to-ace-interviews-72ff0370bb27](https://mageswaran1989.medium.com/a-mind-map-of-dynamic-programming-patterns-to-ace-interviews-72ff0370bb27)