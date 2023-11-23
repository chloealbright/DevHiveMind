---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
There are several types of linked lists, each with its own characteristics and use cases. Here are some common types of linked lists:  
  
1. **Singly Linked List:**  
- Each node points to the next node in the sequence.  
- Example: `1 -> 2 -> 3 -> null`  
  
2. **Doubly Linked List:**  
- Each node has a reference to both the next and the previous node.  
- Example: `null <- 1 <-> 2 <-> 3 -> null`  
  
3. **Circular Linked List:**  
- In a singly or doubly linked list, the last node points back to the first node (forms a loop).  
- Example (singly): `1 -> 2 -> 3 -> 1`  
  
4. **Skip List:**  
- Consists of multiple layers of linked lists, where each layer skips over a fixed number of elements.  
- Used for efficient searching and insertion operations.  
  
5. **Self-adjusting List:**  
- Reorders its elements based on the access pattern to improve performance.  
- Example: Move-to-front list, transpose list.  
  
6. **Unrolled Linked List:**  
- Each node contains an array of elements rather than a single element.  
- Reduces overhead by storing multiple elements in a single node.  
  
7. **XOR Linked List:**  
- Each node stores the XOR combination of addresses of its previous and next nodes.  
- Requires bitwise XOR operation for traversal.  
  
8. **Multi-level Linked List:**  
- Contains multiple levels of linked lists, often used in hierarchical data structures.  
  
9. **Hashed Linked List:**  
- Combines linked lists with hash table concepts for efficient data retrieval.  
  
These are just a few examples, and there may be variations or combinations based on specific requirements in different contexts.