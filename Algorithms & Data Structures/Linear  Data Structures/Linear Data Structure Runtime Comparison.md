---
tags:
  - time
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (52).gif]]
Worst > Average 

**Insertion CREATE/Update for stack and queue runtime depends on how you implement array vs linked list 

	Hash-table O(n)/O(1) = add() 
	
	HashMap O(n)/O(1) = set() 
	
	Set O(n)/O(1) = add() 
	
	Array O(n)/O(n) push() 
	
	Stack O(1)/O(1) = push() 
	
	Queue O(1)/O(1) = enqueue = queue.unshift() 
	
	Singly-Linked List O(1)/O(1) = reassign pointer 
	
	Doubly-Linked List O(1)/O(1) = reassign pointer 

**Searching /Traversal /Lookup (usually index values)** can be used to READ with looping Sorting is a form advance of searching were divide by the length and traverse based on the divide length value of the original data length in order to reorder the data  

	Hash-table O(n)/O(1) = search() or iterate through object 
	
	HashMap O(n)/O(1) = get() or iterate through object 
	
	Set O(n)/O(1) = has() or iterate through object 
	
	Array O(n)/O(n)  
	
	Stack O(n)/O(n) 
	
	Queue O(n)/O(n)  
	
	Singly-Linked List O(n)/O(n)  
	
	Doubly-Linked List O(n)/O(n) 
	
	Binary search applies with sorted values easier to implement recursively which is O(log n) but more efficient with iterative implementation O(1) 

**Access READ for stack and queue runtime depends on how you implement array vs linked list 

	Hash-table might not be able to access 

	HashMap O(n)/O(1) = get() 

	Set O(n)/O(1) = has() more of a search 

	Array O(n)/O(1) = arr[3] 

	Stack O(n)/O(n) = [1,2,3] > arr[Last/FirstIndex] 

	Queue O(n)/O(n) = [1,2,3] > arr[FirstIndex]  -  arr[LastIndex]  

	Singly-Linked List  O(n)/O(n) = head.next.next.next.value 

	Doubly-Linked List O(n)/O(n) = head.prev 

**Deletion DELETE/UPDATE  for stack and queue runtime depends on how you implement array vs linked list 

	Hash-table O(n)/O(1) = remove() 

	HashMap O(n)/O(1) = delete() 

	Set O(n)/O(1) = delete() 

	Array O(n)/O(1) pop() 

	Stack O(n)/O(1) = pop() 

	Queue O(n)/O(1) = dequeue(): pop() 

	Singly-Linked List O(1)/O(1) reassign pointer to null or other node after  

	Doubly-Linked List O(1)/O(1) reassign pointer to null or other node after or before 

## LOOKUP V SEARCH 

A lookup can be a combination of access and search or just search  which can be considered a traversal but they both mean the same thing according to the free dictionary, but they may be are subtle differences.  

Searching is a more general term -- you may not be sure what you will find when you search, or how many things you will find in your result set, 

 But looking up is something you do when you know a record exists and you want to locate one in particular. 

If I were to do a public records search on a person, I might think of that as looking them up. If I were searching for pictures of that person, I would think of it as a search, because there might be bazillions of photos of that person and everyone else with the same name, so the difference is one of expected result. 

Lookup = 1 good match. Search = many possible options. 

There's the (loose) technical distinction between "search" and a LUT (lookup table). 

"Search" describes a process where arbitrary input is used to search across relevant data for partial matches, in order to give back a result set for the user to choose from. 

When using a lookup table, the input is already the key, which will then allow you to retrieve the whole relevant data from the index. 

So the first is bringing you closer, whereas the latter will already retrieve the right thing. 

**Access** is just getting a specific index typically with an array that might be a specific size & you don’t expect it to vary in length or it is sorted and you may be accessing to min or max value 

## ARRAY V STRING 

Array require spaces in memory next to each other while something like a linked list or other data structures with pointers don't need to so you have a node with a value then it has a next pointer next to it in memory which points to some other space in in memory that isn't next to it with its own value this continue until you hit null  

For queue you might want to implement the queue with a linked list since enqueue or pushing at the beginning of a queue would be O(n) when it comes to the linked list you typically would use doubly linked list 

but for stacks since we are pushing and popping at the end so it is ok to use the array but you can use linked list too specifically single linked list  

a string in memory is stored as an array using ascii values were letters are mapped to their values 

string traversal runtime is O(n) space is O(1) like array but space would be O(n) 

string copy which includes some traversal runtime is O(n) space is O(n) 

string access runtime is O(1) space is O(1) like array but space would be O(n) 

no insertion or deletion since immutable   

when a string appears to be mutated it is being copied with a additional value  or is being turned into array and rejoined to new string 

Merging 

sorting O(n log n) 

We store data structures in other data structures to utilize the other functionality of a specific data structures & we benefit from the runtime of that data structure we want to use like storing a graph and a queue or stack or even set  

[https://adrianmejia.com/data-structures-time-complexity-for-beginners-arrays-hashmaps-linked-lists-stacks-queues-tutorial/](https://adrianmejia.com/data-structures-time-complexity-for-beginners-arrays-hashmaps-linked-lists-stacks-queues-tutorial/)




Runtime complexity Search vs Access operation 

It depends on how long it takes to search that particular graph if you're asking specifically for searching, however... I'm not sure whether you could directly state an access operation's time complexity, you can perceive it as a function but all the lines you've noted are O(1) you're accessing the value of the 4th node from the list directly without iterating through it, that's why it's O(1), even if you split them up line-by-line it would still be constant time, a loop through the list would be O(n) though the same goes for the binary tree, algorithms with search it may be logn but accessing a specific part of it without needing to search for it would take constant time  

(this is under the assumption that you're accessing it directly like you're doing here through pointers, if it was through a function or a property that had to loop through the data structure to find the value you're looking for, then that'd be a search algorithm rather than an access operation)






![[unnamed (20).gif]]

### Linear Search Brute Force
The Linear Search algorithm is a set of instructions to traverse the given list and check every element in the list until we find whatever element we are looking for. The technical term for the element we are looking for is - key.  
  
The algorithm goes from the leftmost (or starting) element and continues searching until it either finds the desired element or goes through all the elements in the list.  
  
If the element is found, we will return the position (or index) of the element. If the element we are looking for doesn't exist in the list, we generally return -1.  
  
O(N)