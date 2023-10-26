![[_Images/Algo/GetImage (4).png]]

Worst > Average 

# Tree("CR" U "D") 
Update not in this process directly but with Create & Update you imagine as a form of update within context of Data Structures  

	Insert(Create/Update) — O(n)/O(log(n)) check if less then or greater then 
	
	Access(Read) —  O(n)/O(log(n)) = root.left.right.left.value 
	
	Search —  O(n)/O(log(n)) = recursion or iteration 
	
	Delete(Delete/Update) —  O(n)/O(log(n)) reassign to other node or delete if leaf node reassign to null 
	
	*Average Time Complexity is almost the same for every type of Tree data structure but differs in worst case Time Complexity. 

## Graph(CRUD) Possibly same 

Access   
	
	node.id  
	
	node.edge[1]    
	
	node.edge[2].id        
	
	node.edge 

### Max/Min Heap not considered abstract data type 

	Priority queues  are implement with Heaps also Binary heaps are complete trees  
	
	Array/linkedList > Queues  
	
	Binary Heaps + Queues > Priority queues 
	
	
	Insert(Create/Update)/add — O(log(n))  
	
	Delete(Delete/Update)/remove — O(log(n)) 

Deleting requires to traverse the whole tree to access the element first, then delete it, where the deletion operation itself requires O(LogN). so if you need to delete you only delete the root

	Access(Read)/peek — Min & max Value is O(1) 
	
	Search - dont really need to do but it is O(n) 
	
In searching and deleting, we will have to scan all the elements as they don’t guarantee a specific order, unlike BST.
	
	decrease key O(log(n)) look into 
	
	union O(n) look into 

Binomial heap look into 

	 O(log(n)) for each action 

Fibonacci heap look into 

	 O(1) for each action 
	
	 O(log(n)) delete 

if you're looking for max value in min or vice versa for some reason it would be O(n) because you would need to search as oppose to just accessing to element at the top