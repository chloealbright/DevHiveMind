---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (33).gif]]

Hash Collision is a feature. It arises out of the nature of a hashCode: a mapping from a large value space to a much smaller value space. There are going to be collisions, by design and intent.  
  
Hashes are bound to collide sooner or later, and poor algorithms can make it sooner. That's about it.  
  
  
Not if the hash table is competently written. A hash collision only means that the hashCode is not unique, which puts you into calling equals(), and the more duplicates there are the worse the performance.  
  
Collision Resolution  
--------------  
so you can use linear probing which is part of opening addressing to move from one empty space to the next space until you reach a empty space this uses array  
  
the next resolution is closed addressing which uses linked list  
  
hash function should minimize collusion  
  
  
  
You have to trade off ease of computation against the spread of values. There is no single black and white answer.  
  
[https://en.wikipedia.org/wiki/Hash_table#Collision_resolution](https://en.wikipedia.org/wiki/Hash_table#Collision_resolution)  
  
link list can be used the deal with collision