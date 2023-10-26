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




Hashmap versus map

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