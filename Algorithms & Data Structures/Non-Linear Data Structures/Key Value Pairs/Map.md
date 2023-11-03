---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (42).gif]]
A map is a data structure that stores data in key/value pairs where every key is unique. A map is sometimes called an associative array or dictionary. It is often used for fast look-ups of data. 

the addition of a pair to the collection 
the removal of a pair from the collection 
the modification of an existing pair 
the lookup of a value associated with a particular key 


Hashmap and maps are the same just focus on maps don't need to focus on hashtable as much because it is a legacy data structure class 

hashmap are typically good for improving runtime use binary tree for pre-sorted array also ask if something is sorted  

object/map in JavaScript in general are hashmaps 

HashMap is implemented by ES6 in JavaScript. It has a key-value pair and in both, we can use non-primitive datatype to store the data. The Map will return the key, value pairs in the same order we inserted. Map also have properties and methods like the size of the map and more. 

It is just not called a hash map but still acts as a hashmap 



# Map

In computer science, "map" and "object" can have different meanings depending on the context and programming language being used.  
  
In general, a map is a data structure that stores a collection of key-value pairs, where each key is unique and used to retrieve the associated value. Maps are used to efficiently retrieve and manipulate data based on keys, and they are often implemented using hash tables or other similar data structures.  
  
An object, on the other hand, is a fundamental concept in object-oriented programming (OOP) that represents an instance of a class. Objects are typically used to represent real-world entities or concepts and contain data (in the form of instance variables) and behavior (in the form of methods).  
  
In some programming languages, objects can be used to implement maps or key-value pairs, where the object's instance variables represent the values associated with the keys. In this case, the object is acting as a map or dictionary.  
  
So, while there can be some overlap between the concepts of maps and objects, they are not necessarily the same thing. The use of these terms depends on the specific programming language and context in which they are being used.



"Map" is a general term that can refer to any data structure that allows for the mapping of keys to values. Depending on the implementation, a map may or may not be considered a linear data structure.  
  
For example, in some programming languages, a "map" data structure is a synonym for a "dictionary" or "hash map," which are implemented using a hash table and are therefore not considered linear data structures.  
  
In other cases, a map might be implemented using an ordered data structure, such as a balanced binary search tree, which would make it a non-linear data structure. In this case, the keys would be stored in a specific order to allow for efficient search and traversal.  
  
So, whether a map is considered a linear data structure or not depends on the implementation details of the specific map in question.


## Hashmap versus map

In Java a map is an interface with its own built-in methods in the back and a hash map is it's just a different implementation of the map with its own specific ways it work and built-in methods

Hash table is another implementation of the map interface




The map interface is present in java.util package represents a mapping between a key and a value. The Map interface is not a subtype of the Collection interface. Therefore it behaves a bit differently from the rest of the collection types. A map contains unique keys. 

Maps are perfect to use for key-value association mapping such as dictionaries. The maps are used to perform lookups by keys or when someone wants to retrieve and update elements by keys. Some common scenarios are as follows:  

A map of error codes and their descriptions. 
A map of zip codes and cities. 
A map of managers and employees. Each manager (key) is associated with a list of employees (value) he manages. 
A map of classes and students. Each class (key) is associated with a list of students (value).

![[_Images/Algo/GetImage.png]]

Since Map is an interface, objects cannot be created of the type map. We always need a class that extends this map in order to create an object. And also, after the introduction of Generics in Java 1.5, it is possible to restrict the type of object that can be stored in the Map.  

Map capitalCities = new HashMap();  

	HashMap<String, String> capitalCities = new HashMap<String, String>(); 

	let capitalCities = new Map<string, String>(); 

A Map cannot contain duplicate keys and each key can map to at most one value. Some implementations allow null key and null values like the HashMap and LinkedHashMap, but some do not like the TreeMap. 

The order of a map depends on the specific implementations. For example, TreeMap and LinkedHashMap have predictable orders, while HashMap does not. 

There are two interfaces for implementing Map in java. They are Map and SortedMap, and three classes: HashMap, TreeMap, and LinkedHashMap.

![[Heiarchy.png]]


**LinkedHashMap** is just like HashMap with an additional feature of maintaining an order of elements inserted into it. HashMap provided the advantage of quick insertion, search, and deletion but it never maintained the track and order of insertion which the LinkedHashMap provides where the elements can be accessed in their insertion order. Let’s see how to create a map object using this class. 

  // Creating an empty LinkedHashMap 

        Map<String, Integer> map = new LinkedHashMap<>(); 

        // Inserting pair entries in above Map 

        // using put() method 

        map.put("vishal", 10); 

        map.put("sachin", 30); 

        map.put("vaibhav", 20); 

The **TreeMap** in Java is used to implement the Map interface and NavigableMap along with the Abstract Class. The map is sorted according to the natural ordering of its keys, or by a Comparator provided at map creation time, depending on which constructor is used. This proves to be an efficient way of sorting and storing the key-value pairs. The storing order maintained by the treemap must be consistent with equals just like any other sorted map, irrespective of the explicit comparators. Let’s see how to create a map object using this class. 

	TreeMap<Integer, String> tree_map= new TreeMap<Integer, String>(); 

[https://www.geeksforgeeks.org/treemap-in-java/](https://www.geeksforgeeks.org/treemap-in-java/)



## Dictionaries vs  Maps

1. **Terminology**:
   - **Dictionaries:** The term "dictionary" is commonly used in Python and is sometimes used in other languages like C#. In Python, dictionaries are implemented as a built-in data type and are used to store key-value pairs.
   - **Maps:** The term "map" is more commonly used in languages like Java and C++. In Java, the `Map` interface is part of the Java Collections Framework, and there are various classes that implement this interface (e.g., `HashMap`, `TreeMap`, `LinkedHashMap`).

2. **Data Structures**:
   - **Dictionaries:** In Python, dictionaries are typically implemented as hash tables, offering fast and efficient key-value retrieval.
   - **Maps:** In languages like Java, "Map" is a more generic interface, and it can be implemented using various data structures. For example, `HashMap` uses a hash table, `TreeMap` uses a red-black tree, and `LinkedHashMap` combines a hash table with a linked list.

3. **Key Characteristics**:
   - **Dictionaries:** In Python dictionaries, keys are usually restricted to be of an immutable data type (e.g., strings, numbers, tuples) and are unique within the dictionary. Dictionaries are unordered in Python versions before 3.7 and ordered from Python 3.7 onwards.
   - **Maps:** In the context of Java and other languages, maps often allow more flexibility in the types of keys they can use, but they typically require keys to be unique within the map. Some map implementations maintain order, while others do not.

4. **Usage and Availability**:
   - **Dictionaries:** Python provides built-in support for dictionaries, and they are widely used in Python programs for various purposes.
   - **Maps:** In Java, the Map interface is part of the standard library, making it a common choice for implementing key-value data structures. In other languages, you may need to use external libraries or implement your own map-like data structures.

In summary, dictionaries and maps both serve as key-value data structures, but the terminology and specific characteristics can vary between programming languages. Dictionaries are commonly associated with Python and have specific properties, while maps are more generic and are widely used in languages like Java with various implementations available.