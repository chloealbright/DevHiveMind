![[unnamed (49).gif]]

A binary tree isn't considered a binary tree if it has three individual children on the same level after the root it is only considered a tree if it has at least one or two children after the root, You can build a binary tree using a link list.  
  
There are different types of binary trees like perfect binary trees which are basically trees that doubles after each level and when you get to the end of the tree the sum of the nodes before it plus 1 will equal the total of the last level of notes so everything from the root and other nodes before the last level adds up to the last level sum so for example if you have a root with two children and they have children the root plus its first two children add up to the total of the last level plus one so it would be 3 + 1 which is four which is the total of the last level. this tree is very efficient  
  
Then You have balanced trees which are trees that are no more than one level apart in terms of nodes on each side. if they are more than one level apart then you have an unbalanced tree.  
  
A full binary tree is an unbalanced tree with more nodes on one side than the other and having a difference in levels more than one meaning if you have two nodes after the root on each side then one of the nodes have children and their children have more children but the other one doesn't have any children that is the meaning of having more than one level the root being zero and the initial children being level one and so on  
  
A binary tree is a good middle between array and linked list good with searches and sorting and insertion  
  
  
The complexity of insertion, deletion, and traversing would be O(LogN), and O(N) if the tree is unbalanced.  
  
you can think of the O(LogN) in this case as 2^of the level which will double each time - 1 so log nodes = # of levels or steps  
  
log example log 100 = 2 because 10^2 = 100 that is math behind log