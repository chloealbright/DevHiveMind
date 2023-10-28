---
tags:
  - linear
author: jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
![[unnamed (38).gif]]

![[GetImage (45).png]]

A linked list consists of nodes these nodes consist of the head which contains data and a pointer which is a link to the next node head and so on until you reach the last node which is the tail that points to null 

The atomic unit of the Linked List is called the “node”. This node contains a value and a pointer. The value is simply a number, say 12, while the pointer connects the value to the next node in the chain. Hence the linked part of the Linked List. The first node in the list is known as the head, and the last node with no pointer is known as the tail. 

    LinkedList<String> cars = new LinkedList<String>(); 

alternate linked list need to be built not included in language 

The linked list is considered a recursive function 

Link list and nodes instead are actually scattered all over memory. 

Advantage: Great for adding new nodes and deleting nodes. This is done by changing where the next pointer points. 

Also, a link list is good for memory but in comparison to arrays tend to have better memory 

Linked list maps out memory also storing or using more memory 

A linked list is good for adding things to the list  and don't copy anything to memory like the array 

Kind of like hash tables so iterating through a linked list or traversing through a linked list is usually quite a bit slower than iterating through items like an array even though they're technically both of O(n). 

inserts in the middle of a linked list are a lot better than an array. 

You can also delete nodes very easily versus with an array. 

But the one advantage that it has over hash tables is that there is some sort of order to link list each node points to the next note. So you can have sorted data, unlike a hash table. 

prepend O(1) 

append O(1) 

lookup O(n) 

insert O(n) 

delete O(n) 

Disadvantage: Not too good at retrieving nodes despite knowing the index or searching since each node is only aware of the node next to it. 

You can only go One direction from head to tail not tail to head. It can't be accessed a randomly 

is a linear data structures data that can be accessed sequentially  

Application 

____________ 

The linked list could be used in stack queues and graphs 

Also continues and playback like video playlist or music playlist or just general playing music and going back and forth 

A linked list is used to represent sparse matrices 

You can use the linked list concept to navigate through web pages



Despite their differences in implementation, all types of linked lists maintain a linear sequence of data elements and are therefore considered linear data structures.




Linked List 

May have multiple nodes or linked list you can create Dummy nodes  

Create/Store dummy node which can be used depends on scenario  

Usually something like this:                                 

let previousNode = new ListNode(25);                                                                  

let dummyNode = previousNode;                                                                           

Where the previousNode gets UPDATED                                                        

25 > null             25 > 10 > null                  10 > null                                  

dummy stays intact as more values are added  25 > 10 > null    

If you dont need to use Dummy node then you can Create/ store particularly nodes as prev Node  = Current & current Node = Current.next and you can have multiple prev or current nodes and swap or reassign between them  

Iterate through one or more list so                                                             

while current !== null                                                                                              

if current !== null do something then increment                                  

current= current.next 

Then other business logic the you create new node and update previousNode.next to new node and convert the previousNode head to new node previousNode = new node




LINKED_LIST -> TREE -> GRAPH 

Iterate more using while loop and recursion 

Linked list uses node but with head that rep whole list value and next 

Circular Linked list / Circular Doubly Linked list 

Double linked list bidirectional and has tail  

the head and tail of linked list are null think of it like null boundaries  

tree use node class with left and right and value 

graph built with vertex class with id and edges




Linked list 

A number of linked list problems rely on recursion. If you're having trouble solving a linked list problem, you should explore if a recursive approach will work. Some question will have multiple nodes or linked list 

The “runner” (or second pointer) technique is used in many linked list problems. The runner technique means that you iterate through the linked list with two pointers simultaneously, with one ahead of the other. The fast node might be ahead by a fixed amount, or it might be hopping multiple nodes for each one node that the slow node iterates through. 

Imagine you have two cars running on a road, both of them have to cover the same distance, but one of them, say the faster car moves twice as fast as the slower one. We know that by the time the faster car reaches to the end of the linked list, the slower would be exactly at the middle of the linked list. 

In the acyclic list, the faster pointer reaches the end. In the cyclic list, they both loop endlessly. The faster pointer eventually catches up with and passes the slower pointer. If the fast pointer is ever behind or equal to the slower pointer, you have a cyclic list. If it encounters a null pointer, you have an acyclic list. In outline form, this algorithm looks like this:









```javascript
es6 reverse linked list array destruct 

var reverseList = function(head) { 

  let [prev, current] = [null, head] 

  while(current) { 

      [current.next, prev, current] = [prev, current, current.next] 

  } 

  return prev 

}
```



![[GetImage (46).png]]

Doubly linked list 

Let you go backwards through the list 

It essentially has one more pointer between each node unlike the single list which has one and only goes in one direction the second pointer on the doubly linked list let you go backwards 

Searching through the doubly link list can be more efficient 

Doubly linked list can take up more memory 

You can use a circular doubly linked list to implement a Fibonacci heap 

[https://www.softwaretestinghelp.com/doubly-linked-list-in-java/](https://www.softwaretestinghelp.com/doubly-linked-list-in-java/)




![[GetImage (47).png]]

Circular linked lists 

A circular Linked list is a unidirectional linked list. So, you can traverse it in only one direction. But this type of linked list has its last node pointing to the head node. So while traversing, you need to be careful and stop traversing when you revisit the head node. 

You can implement an image viewer using a circular linked list



![[GetImage (48).png]]

Circular doubly linked lists 

A circular doubly linked list is a mixture of a doubly linked list and a circular linked list. Like the doubly linked list, it has an extra pointer called the previous pointer, and similar to the circular linked list, its last node points at the head node. This type of linked list is the bi-directional list. So, you can traverse it in both directions.