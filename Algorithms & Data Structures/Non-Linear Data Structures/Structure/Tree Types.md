![[tree.gif]]


## Tree(not built into java it has only tree set & tree map ) 

-   A general tree is a tree data structure where there are no constraints on the hierarchical structure. 
    
-   A tree is like a interface and can have limitations depending on the implementations of it that are specific in constraints and features built in 
    
-   Follow properties of a tree. 
    
-   A node can have any number of children. 
    
-   Hierarchy: Root -> Parent  -> Children -> Sibling -> Leaf                                                                            Sub-trees(mini trees after root) typically associated with recursion 
    
-   Child Node: The node which is the immediate successor of a node is called the child node of that node. 
    
-   Leaf Node: The nodes which do not have any child nodes are called leaf nodes.  
    
-   Ancestor of a Node: Any predecessor nodes on the path of the root to that node are called Ancestors of that node. 
    
-   Descendant: Any successor node on the path from the leaf node to that node.  
    
-   Sibling: Children of the same parent node are called siblings. 
    
-   Neighbour of a Node: Parent or child nodes of that node are called neighbors of that node. 
    

## Binary Tree 

-   A binary tree is a tree data structure with constraints were A node can have at most two child nodes (children) known as left and right 
    
-    Is a good middle between array and linked list good with searches and sorting and insertion  
    
-   Used by compilers to build syntax trees. 
    
-   Used to implement expression parsers and expression solvers. 
    
-   Used to store router-tables in routers. 
    
-   If you have one or two children after the root, You can build a binary tree using a link list.  
    
### Types of binary trees  

Perfect binary trees which are basically trees that doubles after each level and when you get to the end of the tree the sum of the nodes before it plus 1 will equal the total of the last level of notes so everything from the root and other nodes before the last level adds up to the last level sum so for example if you have a root with two children and they have children the root plus its first two children add up to the total of the last level plus one so it would be 3 + 1 which is four which is the total of the last level. this tree is very efficient.  

Balanced trees which are trees that are no more than one level apart in terms of nodes on each side. if they are more than one level apart then you have an Unbalanced tree. 

Full binary tree is an unbalanced tree with more nodes on one side than the other and having a difference in levels more than one meaning if you have two nodes after the root on each side then one of the nodes have children and their children have more children but the other one doesn't have any children that is the meaning of having more than one level the root being zero and the initial children being level one and so on  

The complexity of insertion, deletion, and traversing would be O(LogN), and O(N) if the tree is unbalanced. You can think of the O(LogN) in this case as 2^of the level which will double each time - 1  so log nodes = # of levels or steps.  

# Binary Search Tree 

-   A binary search tree is a more constricted extension of a binary tree. 
    
-   Follow properties of a binary tree. 
    
-   Has a unique property known as the binary-search-tree property. This property states that the value (or key) of the left child of a given node should be less than or equal to the parent value and the value of the right child should be greater than or equal to the parent value. 
    
-   Used to implement simple sorting algorithms. 
    
-   Can be used as priority queues. 
    
-   Used in many search applications where data are constantly entering and leaving. 
    
## Pros 
    -   Inserting and deleting 
        
    -   Speed of Access 
        
    -   Maintains sorted order; retrieval of elements is in order. 
        
    -   Flexible size 
        
## Cons 
    
    -   Some overhead because of their creation and management. 
        
    -   Like I could become unbalanced and basically be a long live list which can cause things to become O(n) and there is no O(1) operations  
        
	-   In production we probably won't be using a binary search tree will be using AVL or red-black tree since they self-balance 
    
# Binary Search on Arrays 
    
    -   Binary search is often presented as a search method for sorted arrays. This does not contradict the description above. In fact, it highlights the fact that we don't actually care how a binary search tree is implemented; we just care that we can take an object and do three things with it: get a element, get a left sub-object, and get a right sub-object (subject, of course, to the constraints about the elements in the left being less than the element, and the elements in the right being greater, etc.). 
        
    
    -   We can do all three things with a sorted array. With a sorted array, the "element" is the middle element of the array, the left sub-object is the subarray to the left of it, and the right sub-object is the subarray to the right of it. E.g., the array 
        
    
    -   As often presented, binary search refers to the array-based algorithm presented here, and binary search tree refers to a tree-based data structure with certain properties. However, the properties that binary search requires and the properties that binary search trees have to make these two sides of the same coin. Being a binary search tree often implies a particular implementation, but really it's a matter of providing certain operations and satisfying certain constraints. Binary search is an algorithm that functions on data structures that have these operations and meet these constraints. 
        

# AVL tree 

-   An AVL tree is a self-balancing binary search tree. This is the first tree introduced which automatically balances its height. 
    
-   Follow properties of binary search trees. 
    
-   Self-balancing. 
    
-   Each node stores a value called a balance factor which is the difference in height between its left subtree and right subtree. 
    
-   All the nodes must have a balance factor of -1, 0 or 1. 
    
-   Used in situations where frequent insertions are involved. 
    
-   Used in Memory management subsystem of the Linux kernel to search memory regions of processes during preemption. 
    

# Red-black tree 

-   A red-black tree is a self-balancing binary search tree, where each node has a colour; red or black. The colours of the nodes are used to make sure that the tree remains approximately balanced during insertions and deletions. 
    
-   Follow properties of binary search trees. 
    
-   Self-balancing. 
    
-   Each node is either red or black. 
    
-   The root is black (sometimes omitted). 
    
-   All leaves (denoted as NIL) are black. 
    
-   If a node is red, then both its children are black. 
    
-   Every path from a given node to any of its leaf nodes must go through the same number of black nodes. 
    
-   As a base for data structures used in computational geometry. 
    
-   Used in the Completely Fair Scheduler used in current Linux kernels. 
    
-   Used in the epoll system call implementation of Linux kernel. 
    

# Splay tree 

-   A splay tree is a self-balancing binary search tree. 
    
-   Follow properties of binary search trees. 
    
-   Self-balancing. 
    
-   Recently accessed elements are quick to access again. 
    
-   After performing a search, insertion or deletion, splay trees perform an action called splaying where the tree is rearranged (using rotations) so that the particular element is placed at the root of the tree. 
    
-   Used to implement caches 
    
-   Used in garbage collectors. 
    
-   Used in data compression 
    

# Treap 

-   A treap (the name derived from tree + heap) is a binary search tree. 
    
-   Each node has two values; a key and a priority. 
    
-   The keys follow the binary-search-tree property. 
    
-   The priorities (which are random values) follow the heap property. 
    
-   Used to maintain authorization certificates in public-key cryptosystems. 
    
-   Can be used to perform fast set operations. 
    

# B-tree 

-   B tree is a self-balancing search tree and contains multiple nodes which keep data in sorted order. Each node has 2 or more children and consists of multiple keys. 
    
-   1. Every node x has the following: 
    
    -   — x.n (the number of keys) 
        
    -   — x.keyᵢ (the keys stored in ascending order) 
        
    -   — x.leaf (whether x is a leaf or not) 
        
    

2. Every node x has (x.n + 1) children. 

3. The keys x.keyᵢ separate the ranges of keys stored in each sub-tree. 

4. All the leaves have the same depth, which is the tree height. 

5. Nodes have lower and upper bounds on the number of keys that can be stored. Here we consider a value t≥2, called minimum degree (or branching factor) of the B tree. 

— The root must have at least one key. 

— Every other node must have at least (t-1) keys and at most (2t-1) keys. Hence, every node will have at least t children and at most 2t children. We say the node is full if it has (2t-1) keys. 

The last of the behavior modeling structures good for sorting problems and halving problems and other things O(log(n)) 

A tree is a hierarchy like a Linux file system consisting of nodes there are many types of trees
