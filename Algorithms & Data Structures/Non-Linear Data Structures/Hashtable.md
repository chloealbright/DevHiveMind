---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (35).gif]]

A key Value Pair made in heaven

A hash table (often called a hash map) is a data structure that maps keys to values. This is similar to an object in JavaScript and a dictionary in Python language.  
  
In this type of data structure, you give the hash-map a key which can be a word and it retrieves the definition or the value for you. Under the hood, it works a lot like an array. The key gets run through the function called the “hashing function” that spills out the memory location for you making it random access.  
  
A hash table is a map data structure that contains key/value pairs. It uses a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.  
  
hash tables are made up of two parts it is basically a combination of an array and a linked list stored inside of it. more specifically it is :  
  
An object with the table where the data is stored. The array holds all the key-value entries in the table. The size of the array should be set according to the amount of data expected.  
  
Hash function (or mapping function): This function determines the index of our key-value pair. It should be a one-way function and produce a different hash for each key.  
  
  
The performance of a hash table depends on three fundamental factors: hash function, size of the hash table, and collision handling method.  
  
The way it’s different is that these memory locations need not be next to each other, rather can be anywhere. Therefore, there’s no issue with the increase in size. However, there is a different problem — depending on the hashing algorithm you use, two keys could hash to the same memory location. This is what’s known as a “collision” and there are multiple ways to resolve them but again, it’s all happening under the hood.  
  
  
  
The hash function usually takes a string as input and it outputs a numerical value. The hash function should always give the same output number for the same input. When two inputs hash to the same numerical output, this is called a collision. The goal is to have few collisions.  
  
Hash set are better than sets specifically in java and javascript has set objects  
  
So when you input a key/value pair into a hash table, the key is run through the hash function and turned into a number. This numerical value is then used as the actual key that the value is stored by. When you try to access the same key again, the hashing function will process the key and return the same numerical result.  
  
The number will then be used to look up the associated value. This provides a very efficient O(1) lookup time on average.  
it is also O(1) for insertion, delete, and search.  
  
Advantage: As we have learned, hash maps are great for adding and retrieving.  
  
Disadvantage: May cause collision of keys.  
  
  
hashtable is indexed like an array but the key value pair or specifically the key is assigned a index by getting the modulo of that key -1 and array length  
  
but you can end up with collisions were we assign pairs to the same index in that case it kinds of ends like an array of linked list nodes this where hashing function comes in and reduce the collisions  
index: 0, 1, 2  
[node("fhg), 5, node(5)]  
V V V > pointes to key when at same index  
node("gch) node("8)  
  
  
  
  
[https://www.youtube.com/watch?v=KyUTuwz_b7Q&t=311s](https://www.youtube.com/watch?v=KyUTuwz_b7Q&t=311s)