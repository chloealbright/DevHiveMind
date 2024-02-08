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

## Traversing a Set

```javascript
const myArray = [1, 2, 3, 4, 5, 5];  
const mySet = new Set();  
  
// Adding values from the array into the set during each iteration  
for (const value of myArray) {  
mySet.add(value);  
}  
  
// If needed, retrieve all values from the set  
const valuesInSet = Array.from(mySet);  
  
// Calculate the sum using reduce  
const sum = valuesInSet.reduce((acc, value) => acc + value, 0);  
  
console.log(sum);
```

The order in which `Array.from` gets values from a Set is based on the order in which the Set iterates through its values. Sets, like arrays, maintain the order of insertion, so the order of values in the resulting array will correspond to the order in which they were added to the Set.  
  
Regarding the terms "traverse" and "iteration":  
  
- **Iteration:**  
- Iteration refers to the process of accessing each element in a collection one at a time. In the context of programming, iteration is commonly associated with loops or other constructs that allow you to go through each item in a sequence, like a for loop or the `for...of` loop in JavaScript.  
  
- **Traverse:**  
- Traverse generally means to move through or go across a data structure. It's a broader term that encompasses iteration but isn't limited to accessing elements in a specific order. It can involve moving through elements in any manner, including forwards, backwards, or based on certain conditions.  
  
In the context of data structures like arrays or sets:  
  
- **Traversal of an array:**  
- Typically involves moving from the first element to the last or vice versa. This is commonly associated with the concept of indexes.  
  
- **Iteration over a set:**  
- In the case of sets, iteration often involves accessing elements one by one in the order in which they were added to the set. Sets do not have indexes like arrays, so the order is based on the internal structure that maintains uniqueness.  
  
In summary, while the terms are related, iteration is a specific form of traversal that involves accessing elements sequentially, and traversal is a broader term that encompasses various ways of moving through elements in a data structure. The order in `Array.from` reflects the order in which the Set iterates through its elements.

## Pros

- Efficient for checking membership and value existence.

- Prevents duplicates and offers a more efficient way to store elements in a set compared to adding them individually.

- The complexity of checking if a value is contained in the set depends on the underlying data structure. For instance, in C++, a binary search tree is used, resulting in O(log(N)) time complexity.

## Cons

- Sets have intentional limitations and are not suitable for a wide range of use cases.
- They are also not traverse-able meaning you cant iterate through it in specific order like an array were you iterate at the beginning or end or even the middle like if you wanted to do some sort of binary search which isn't possible because of the structure of a set. But sets are iterable like in the example above.

