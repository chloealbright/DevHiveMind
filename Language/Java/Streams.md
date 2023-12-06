![[streamline.png]]

stream is an ordered sequence of data

that Provides a common I/O model

also Abstract details Of underlying source or destination

Stream handles iteration in Java


Stream types are unidirectional

You will either read from or write to a stream

2 categories of streams

Byte streams

Interact as binary data 01101110

Text streams


general interaction is the same for both stream types

![[Pasted image 20230422142413.png]]

![[s1.png]]

![[s2.png]]

![[R1.png]]

![[W1.png]]


![[R1c.png]]

![[W1c.png]]

![[RAB.png]]

![[RAC.png]]

There are several types of stream operations in Java, including:

1.  Intermediate operations: They process the data elements in a stream and return a new stream. Example: filter, map, flatMap, sorted, etc.
2.  Terminal operations: They produce a result from a stream and don’t return another stream. Example: forEach, count, min, max, reduce, etc.
3.  Short-circuiting operations: They return as soon as a result is produced, and don’t process the rest of the elements. Example: findFirst, findAny, anyMatch, allMatch, noneMatch, etc.
4.  Stateful operations: They process the data elements in a non-linear, stateful manner and may produce different results for the same input. Example: distinct, peek, etc.
5.  Collecting operations: They collect elements from a stream into a container such as a list, set, map, etc. Example: collect, toArray, toList, toSet, toMap, etc.

![[clean.png]]

![[Pasted image 20230422143527.png]]

![[Pasted image 20230422143549.png]]

![[SmartSelect_20230224_011200_Pluralsight.jpg]]

![[SmartSelect_20230224_011256_Pluralsight.jpg]]

![[tempFileForShare_20230225-131101.jpg]]

![[tempFileForShare_20230225-131329.jpg]]

![[tempFileForShare_20230225-131437.jpg]]

![[tempFileForShare_20230224-010340.jpg]]

![[tempFileForShare_20230225-131753.jpg]]

![[tempFileForShare_20230225-132221.jpg]]

![[tempFileForShare_20230225-132100.jpg]]

![[tempFileForShare_20230225-131636.jpg]]