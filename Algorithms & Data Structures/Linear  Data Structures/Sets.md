---
tags:
  - linear
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (26).gif]]

The set data structure stores values without any particular order and with no repeated values. Besides being able to add and remove elements to a set, there are a few other important set functions that work with two sets at once. 

Sets are a new object type with ES6 (ES2015) that allows the creation of collections with unique values. The values in a set can be either simple primitives like strings or integers as well as more complex object types like object literals or arrays. It also doesn't contain an index 

```Java
HashSet<String> cars = new HashSet<String>(); 

Set<Integer> set = new HashSet<Integer>(); 
```

A Set represents a generic "set of values". A TreeSet is a set where the elements are sorted (and thus ordered), a HashSet is a set where the elements are not sorted or ordered. 

A HashSet is typically a lot faster than a TreeSet. 

A TreeSet is typically implemented as a red-black tree , whereas a HashSet uses Object.hashCode() to create an index in an array. Access time for a red-black tree is O(log(n)) whereas access time for a HashSet ranges from constant-time to the worst case (every item has the same hashCode) where you can have a linear search time O(n). 
```Java
TreeSet ts = new TreeSet();  
```

[https://www.geeksforgeeks.org/treeset-in-java-with-examples/](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 

**Union** — This combines all the items from two different sets and returns this as a new set (with no duplicates). 

**Intersection** — Given two sets, this function returns another set that has all items that are part of both sets. 

**Difference **— This returns a list of items that are in one set but NOT in a different set. 

**Subset**— This returns a boolean value that shows if all the elements in one set are included in a different set. 

**SET** used for parsing duplicates can pass arrays, string, and maybe objects for other data structures 

# Pros 

    Checking membership; value existence. 

     Avoids duplicates and you can also store things in a set instead of adding elements one by one into a set 

The complexity of checking if a value contained in the set depends on the underlying data structure used to implemented the set. 

In C++, It uses a binary search tree (probably a red black tree; a type of self balancing binary search tree). So, the complexity would be O(LogN), and O(N) if the tree is unbalanced. 

In Java, HashSet class implements the Set Interface using the hash table data structure. So, the complexity would be same as the hash tables(see above). 

# Cons 

Sets are intentionally limited. There isn’t much you can do with them. So,  there are terrible at almost everything else.