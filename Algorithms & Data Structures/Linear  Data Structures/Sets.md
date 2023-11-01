---
tags:
  - linear
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
**Set Data Structure and its Functions**

The set data structure is designed to store values without any specific order and with no repeated values. In addition to basic operations like adding and removing elements, there are several important set functions that work with two sets simultaneously.

Sets, introduced as a new object type in ES6 (ES2015), enable the creation of collections with unique values. The values in a set can range from simple primitives like strings and integers to more complex object types, such as object literals or arrays. Notably, sets do not rely on indices.

```Java
HashSet<String> cars = new HashSet<String>();
Set<Integer> set = new HashSet<Integer>();
```

A Set represents a generic "set of values." There are different types of sets, such as TreeSet and HashSet, with distinct characteristics. A TreeSet maintains sorted and ordered elements, while a HashSet does not impose any particular order. HashSet is typically faster than TreeSet.

A TreeSet is typically implemented as a red-black tree, resulting in an access time of O(log(n)). In contrast, a HashSet utilizes Object.hashCode() to create an index in an array, with access times ranging from constant-time to the worst-case scenario, where every item has the same hashCode, leading to linear search time (O(n)).

```Java
TreeSet ts = new TreeSet();
```

Learn more about TreeSet in Java: [TreeSet in Java with Examples](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

**Set Operations**

- **Union**: Combines items from two sets, creating a new set with no duplicates.

- **Intersection**: Returns a set containing items present in both input sets.

- **Difference**: Provides a list of items in one set but not in another.

- **Subset**: Indicates whether all elements of one set are included in another.

Sets are commonly used for eliminating duplicates and can accommodate arrays, strings, and potentially objects for other data structures.

## Pros

- Efficient for checking membership and value existence.

- Prevents duplicates and offers a more efficient way to store elements in a set compared to adding them individually.

- The complexity of checking if a value is contained in the set depends on the underlying data structure. For instance, in C++, a binary search tree is used, resulting in O(log(N)) time complexity.

## Cons

Sets have intentional limitations and are not suitable for a wide range of use cases.



