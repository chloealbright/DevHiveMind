---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (36).gif]]![[unnamed (37).gif]]

A dictionary uses a key to reference the value directly inside of an associative array.  
  
i.e (KEY => VALUE)  
  
A hash is more often described as a hash table that uses a hash function to calculate the position in memory (or more easily an array) where the value will be. The hash will take the KEY as input and give a value as output. Then plug that value into the memory or array index.  
  
i.e KEY => HASH FUNCTION => VALUE  
  
I guess one is direct while the other isn't. Hash functions may not be perfect either and may sometimes provide an index referencing the wrong value. But that can be corrected.  
  
A dictionary is a general concept that maps keys to values. There are many ways to implement such as mapping.  
  
A hashtable is a specific way to implement a dictionary.  
  
Besides hashtables, another common way to implement dictionaries is red-black trees.  
  
Each method has its own pros and cons. A red-black tree can always perform a lookup in O(log N). A hashtable can perform a lookup in O(1) time although that can degrade to O(N) depending on the input.  
  
  
hashmap is an array of linked list