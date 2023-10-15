![[Collections-in-Java1.png]]
### Background

The standard objects for grouping Java objects were done using the Array, Vector, and Hashtable classes. These could not be easily extended and did not have a standard member interface. In Java 1.2, the Collections Framework was introduced to address the need for reusable collection data structures.

The Java Collections Framework is a unified architecture for representing and manipulating collections in a standard way. A collection, like a container, is an object that represents a group of objects. For example, think of a list of Technologist’s names or one of my favorites, a jar of cookies.

The Java Collections Framework allows developers to have a standard way to add objects to a collection, remove objects from a collection, search for objects in the collection, get objects from the collection and iterate through the collection.

https://www.geeksforgeeks.org/collections-in-java-2/

### Benefits

Using the Collections Framework has the following benefits:

-   It reduces programming effort and increases productivity because the developer can use the provided data structures and algorithms.
-   Increases software reuse and standardization, which in turn increases code quality.

### How to choose a suitable collection?

Here are a few questions to consider when deciding on which collection to use:

-   Is order important?
-   Are duplicates OK?
-   Does it need to be accessed by multiple threads?
-   Do you need fast adding and removing elements?

### Collections Framework

The Collections Framework consists of:

-   Interfaces represent the different types of collections: sets, lists, queues, and maps. These are divided into two groups:

-   Basic ****interfaces found in java.util.Collection. It has the Set, List, and Queue interfaces.
-   Collection-view interfaces are not authentic collections but enable them to be manipulated as collections found in ****java.util.Map. It has a Map interface.

-   Various implementations:

-   General-purpose is the primary implementation of collection interfaces.
-   Legacy - Vector and Hashtable were retrofitted to implement the collection interfaces.
-   Special-purpose - displays nonstandard performance characteristics, usage restrictions, or behavior.
-   Concurrent - designed for highly concurrent use.
-   Wrapper adds functionality to other implementations.
-   Convenience - high-performance mini implementations.
-   Abstract are partial implementations of the collection interfaces for creating custom implementations.

-   Algorithms of static methods perform valuable functions on collections, such as searching and sorting.
-   Infrastructure interfaces that provide support for the collection interface.
-   Array Utilities for arrays of primitive types and reference objects that rely on the collections framework. Remember, these are not collections.

#### ArrayList

-   [ArrayList](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/ArrayList.html) class is a resizable array. The built-in Array doesn’t allow you to change the size. ArrayList stores elements as an ordered collection. Use it for storing and accessing data. Valuable methods:

-   Elements are added using the add(), set method to change the elements,
-   remove elements using remove(),
-   to know the size of the ArrayList, use the size() and
-   sort() to sort alphabetically and numerically.

[ArrayList (Java SE 16 & JDK 16)](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/ArrayList.html)

#### LinkedList

-   [LinkedList](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/LinkedList.html) class is a resizable list. It stores its elements in containers. It should be used to manipulate data. Valuable methods:

-   addFirst() to add elements to the beginning of the list,
-   addLast() to add elements to the end of the list,
-   removeFirst() to remove from the beginning of the list,
-   removeLast() to remove elements from the end of the list,
-   getFirst() to get the first element and
-   getLast() to get the last element.

[LinkedList (Java SE 16 & JDK 16)](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/LinkedList.html)

#### HashSet

-   [HashSet](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/HashSet.html) is a set  implemented as a hash table . It returns elements in random order and allows null values. Useful methods:

-   To add elements, use add(),
-   check if an element exists, use contains(),
-   to remove an item, use remove(),
-   to remove elements, use clear(),
-   to know how many elements, use size() use a for-each loop to loop through the HashSet.

-   To learn more about HashSet, see Oracle Java [Documentation](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/HashSet.html). Follow [these instructions](https://www.w3schools.com/java/java_hashset.asp) for hands-On with HashSet.

#### TreeSet

-   [TreeSet](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/TreeSet.html) is similar to HashSet, except it sorts the elements in ascending order. Useful methods:

-   To add elements, use add(),
-   check if an element exists, use contains(),
-   to remove an item, use remove() to remove elements,
-   use clear() to know how many elements,
-   use size() and a for-each loop to loop through the TreeSet.

-   To learn more about TreeSet, see Oracle Java [Documentation](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/TreeSet.html).

-   In Eclipse, create a TreeSet example based on the one here:

[https://lh6.googleusercontent.com/fcWiLGfFWRlW42i0_acLaZVFI6FIddiXHx3HiLlUFjKX5L4XAjrTMOjy2mL7opIQHEGOOpljBYA7n-OmZzkx81Bbx5Xg5Mb5l8_HyVtZayv_Voh6U5FZCOIx0-AortozFcDQeXvw9PnN3_ubkg](https://lh6.googleusercontent.com/fcWiLGfFWRlW42i0_acLaZVFI6FIddiXHx3HiLlUFjKX5L4XAjrTMOjy2mL7opIQHEGOOpljBYA7n-OmZzkx81Bbx5Xg5Mb5l8_HyVtZayv_Voh6U5FZCOIx0-AortozFcDQeXvw9PnN3_ubkg)

#### HashMap

-   [HashMap](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/HashMap.html) stores elements in key/value pairs and can be accessed by an index of another type. It can store different types(string key Integer value or the same types (string key/value). Useful methods:

-   To add elements, use put(),
-   get() to access a value,
-   remove() to remove an element,
-   clear() to remove all items,
-   size() how many elements and loop through elements using a for-each loop.

-   To learn more about HashSet, see Oracle Java [Documentation](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/HashMap.html). Follow [these instructions](https://www.w3schools.com/java/java_hashmap.asp) for hands-On with HashMap.

#### PriorityQueue

-   A [queue](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/Queue.html) is used to hold elements before processing.   A queue uses First In First Out (FIFO) for processing elements. The queue is an interface, so we create either PriorityQueue or LinkedList. Useful methods:

-   To add elements, use add(),
-   check if element exists, use contains(),
-   to remove an item, use remove(),
-   to remove elements, use clear(),
-   to know how many elements, use size() use a for-each loop to loop through the PriorityQueue or LinkedList.

-   To learn more about Queue, see Oracle Java [Documentation](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/Queue.html).