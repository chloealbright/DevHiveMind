---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Abstract Data.gif]]

Abstract Data Types are entities that are definitions of data and operations but do not have implementation details.  
  
meaning there is knowledge of the data and the operations that can be performed but since there are different languages we can specify implementation details differently because it varies from language to language.  
  
so let's say you have a smartphone its abstract or logical view is basically its tech specs like ram, processor screen size, etc ...  
  
then when you go deeper you have operations or methods/functions for calling(), text(), video(), and so on  
  
then you have the implementation which would basically be the syntax and its general structure including variables.  
  
lets say you have an array the abstract would be the array data type , index size position, and memory address and being able to read, modify and sort through the array  
  
then you have the implementation which would be the syntax depending on the language  
  
Abstract Data Types when it comes to Data Structure  
  
A lot of Data Structures are considered Concrete Data Type (CDT) where it contains an implementation of ADT. But there are Data Structure that can be implemented in several ways and its implementation may vary from language to language.  
  
Abstract data types, commonly abbreviated ADTs, are a way of classifying data structures based on how they are used and the behaviors they provide. They do not specify how the data structure must be implemented but simply provide a minimal expected interface and set of behaviors.  
  
Abstract Data Type(ADT) is a data type, where only behavior is defined but not implementation meaning as long as you do certain behavior like for a stack push and pop we don't care about how you implement or create push and pop  
  
Examples:  
Array, List, Map, Queue, Set, Stack, Table, Tree, and Vector are ADTs. Each of these ADTs has many implementations i.e. CDT. The container is a high-level ADT of above all ADTs.  
  
Linked List is an Abstract Data Type (ADT) that holds a collection of Nodes, the nodes can be accessed in a sequential way. Linked List doesn’t provide a random access to a Node.  
  
ADT — Interface  
The Linked List interface can be implemented in different ways, is important to have operations to insert a new node and to remove a Node:  
  
Since abstract data types don’t specify an implementation, this means it’s also incorrect to talk about the time complexity of a given abstract data type.  
  
ADT — Operations  
Traversal : You must be thinking, “how could I print all the elements of a Linked List?”  
A Linked List can be traversed , is possible to navigate in the list using the nodes next element.  
  
stack , and queues are considered abstract to