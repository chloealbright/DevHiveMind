---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
If input array is sorted then 

-   Binary search focus on middle 
    
-   Two pointers 
    

If given a linked list then 

-   Two pointers | Fast Slow 
    

If recursion is banned then 

-   Stack 
    

Dynamic programming 

-   If asked for maximum/minimum subarray/subset/options then 
    
-   Use Stacks depending on situation like match parentheses question 
    

Heap 

-   If asked for top/least K items then 
    

Priority queues 

-   can be used with certain implementations of Dijkstra’s Shortest Path 
    
-   When you need to fetch next best or worst element 
    
-   Huffman coding which is used for lossless data compression 
    
-   Best First Search  
    
-   Minimum spanning tree 
    

If asked for common strings then 

-   Map 
    
-   Trie 
    

Bfs is faster than DfS when it comes to tree with depth  

Graph 

-   DFS 
    
-   BFS 
    

Dfs good for  

-   Topological sorting 
    
-   Maze 
    
-   Finding strongly connected components 
    
-   Generating words in order 
    
-   If solutions are frequent but located deep in the tree 
    
-   If the tree is very wide mean spread out  
    
-   Checking if a path exist 
    
-   Uses less memory but can get slow  
    

Bfs 

-   Shortest Path 
    
-   Copying garbage collection 
    
-   Serialization 
    
-   Finding  closes node  
    
-   If the tree is very deep and solutions are rare 
    
-   If you know a solution is not far from the root of the tree: 
    
-   Use more memory 
    

Dijkstra’s & Bellman-Ford 

-   Shortest path 
    

Backtracking 

-   If asked for all permutations/subsets then 
    
-   Typically reserved for Sudoku games or chess something with a grid  like many board games for mobile platforms or websites that have those games 
    

Cyclic sort 

-   When given number from range 1 to n  
    
-   Store one or more different values in the same pointer 
    
-   Swap corresponding values 
    
-   Solve in-place then 
    
-   Cyclic sort won't always sort completely because in the case were you are sorting an array with missing numbers in its range the logic wont fully work because of missing numbers and it won't be fully sorted because of this 
    
-   Cycle Sort (opens new window)is sorting algorithm which uses comparison sort (opens new window)that is theoretically optimal in terms of the total number of writes to original array, unlike any other in-place sorting algorithm.  
    
-   Cycle sort is unstable sorting algorithm. It is based on idea of permutation in which permutations are factored into cycles, which individually rotate and return a sorted output. 
    
-   This sorting algorithm is best suited for situations where memory write or swap operations are costly. 
    

Merge Interval 

-   The merge interval technique is powerful, addressing many common scheduling or interval problems. This approach can be used as subproblem for many real world scenarios. For example: Scheduling and assigning rooms for classes or meetings. 
    
-   Organizing data in memory and calculating allocated and free spaces. 
    
-   Task scheduling in operating systems. 
    

intervalOneIdx = 0                                                                                     

const [firstIntStart, firstIntEnd] = firstList[intervalOneIdx]   firstIntStart= 0:[row][col],    

firstIntEnd = 1:[row][col]  = [   row = [0, 1]    ]; 

Sort Scenario 

-   Sort 10 schools around your house by distance: insertion sort 
    
-   Ebay sorts listings by the current Bid amount: radix or counting sort 
    
-   Sort scores on ESPN: Quick sort 
    
-   Massive database (can't fit all into memory) needs to sort through past year's user data: Merge Sort 
    
-   Almost sorted Udemy review data needs to update and add 2 new reviews: Insertion Sort 
    
-   Temperature Records for the past 50 years in Canada: radix or counting Sort or Quicksort if decimal places 
    
-   Large user name database needs to be sorted. Data is very random: Quicksort 
    
-   You want to teach sorting: Bubble sort 
    

If it's a sorted array, use Binary tree to achieve O(log N). Divide and Conquer - Divide a data set into smaller chunks and then repeating a process with a subset of data. Binary search is a great example of this 

Hash Maps are usually the answer to improve Time Complexity 

Hash tables and precomputed information (i.e. sorted) are some of the best ways to optimize your code