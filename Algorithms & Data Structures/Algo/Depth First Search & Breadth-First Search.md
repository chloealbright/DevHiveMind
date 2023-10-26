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
---
![[unnamed (43).gif]]

DFS “is an algorithm for traversing or searching tree data structure. One starts at the root and explores as far as possible along each branch before backtracking.” — Wikipedia  
  
DFS explores a path all the way to a leaf before backtracking and exploring another path. Let’s take a look at an example with this type of traversal.  
  
  
  
BFS “is an algorithm for traversing or searching tree data structure. It starts at the tree root and explores the neighbor nodes first, before moving to the next level neighbors.”  
  
BFS algorithm traverses the tree level by level and depth by depth.  
the BF-queue makes recursion more complex then with DFSTACKS but is possible but sticking with Iterative approach is easier to implement  
  
  
Breadth-first traversal traditionally uses a queue, not a stack. The nature of a queue and a stack are pretty much opposite, so trying to use the call stack (which is a stack, hence the name) as the auxiliary storage (a queue) is pretty much doomed to failure, unless you're doing something stupidly ridiculous with the call stack that you shouldn't be.  
  
On the same token, the nature of any non-tail recursion you try to implement is essentially adding a stack to the algorithm. This makes it no longer breadth first search on a binary tree, and thus the run-time and whatnot for traditional BFS no longer completely apply. Of course, you can always trivially turn any loop into a recursive call, but that's not any sort of meaningful recursion.  
  
However, there are ways, as demonstrated by others, to implement something that follows the semantics of BFS at some cost. If the cost of comparison is expensive but node traversal is cheap, then as @Simon Buchan did, you can simply run an iterative depth-first search, only processing the leaves. This would mean no growing queue stored in the heap, just a local depth variable, and stacks being built up over and over on the call stack as the tree is traversed over and over again. And as @Patrick noted, a binary tree backed by an array is typically stored in breadth-first traversal order anyway, so a breadth-first search on that would be trivial, also without needing an auxiliary queue.  
  
  
BFS considers all neighbors first and therefore not suitable for decision making trees used in games or puzzles.  
  
DFS is more suitable for game or puzzle problems. We make a decision, then explore all paths through this decision. And if this decision leads to win situation, we stop.  
  
QUEUE -> LinkedList or arrays which you should avoid -> bfs  
  
use shift(removes first) = like pop(removes last) = dequeue(built function) better but have to build  
  
use unshift(adds to beginning) = like push(adds to end) = enqueue(built function)  
  
STACK -> LinkedList or Array depends -> dfs  
use pop and push  
  
the linked list memory is dynamic and array is faster  
  
  
The most important points is, BFS starts visiting nodes from root while DFS starts visiting nodes from leaves. So if our problem is to search something that is more likely to closer to root, we would prefer BFS. And if the target node is close to a leaf, we would prefer DFS.