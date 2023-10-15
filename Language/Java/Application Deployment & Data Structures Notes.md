Eclipse javafx module 

-------------------------------------------- 

--module-path /usr/share/openjfx/lib --add-modules=javafx.controls,javafx.fxml 

run jar in terminal 

--------------------------- 

java --module-path /usr/share/openjfx/lib --add-modules=javafx.controls,javafx.fxml -jar tictactoe-carpentier-joshua.jar 

extracting a JAR file: To extract the files from a .jar file , we can use: 

jar xf jarfilename 

Data access object DAO 

------------------------------------ 

look at old code from Boulet class pay attention to structure and naming convention 

Try to Have package be less dependent on each other otherwise make it secure. Also be aware of maintenance. 

Stick to Java 1.8  

packages can contain jars 

lib file is created to store your jar files 

Maven is a central repo  for dependencies and a universal build system 

there are alternatives like Gradle which is used in android and is json- JavaScript Object Notation  based or Ant which is xml based like maven but is more flexible  

do JUnit test first and try limit classes to 150 lines and methods to 20 and 50 lines 

Java class  implementation 

when implementing class java hover mouse over class to utilize the method instead of pasting in or turning the class abstract 

code tip 

make code robust or just do it however you do it and try to 

Refactor that code and older code  you worked on by trying to use less lines as possible and make the code more efficient 

java.util.Arrays class, are: 

    Searching an array for a specific value to get the index at which it is placed (the binarySearch method). 

    Comparing two arrays to determine if they are equal or not (the equals method). 

    Filling an array to place a specific value at each index (the fill method). 

    Sorting an array into ascending order. This can be done either sequentially, using the sort method, or concurrently, using the parallelSort method introduced in Java SE 8. Parallel sorting of large arrays on multiprocessor systems is faster than sequential array sorting. 

ArrayList 

---------------------------- 

with arrays you can only use primitive types like int, double, string, or etc ..... 

when Declaring Arraylist <Number> which is considered a collection, in this case the Number collection cant use primitive types they use Object type data types like Integer or Double ex. 

Arraylist <Integer> num = new Arraylist <> (); 

also Array list aren't a fixed size like arrays 

POJO- plain old java object basically creating a private variable and building a constructor and getters and setters 

Questions to answer  

1.Number of Products sold in NY. 

2.Number of Product sold in CT. 

3.Number of People who bought more than 10 products. 

4.Number of People who spent more than2,000.00. 

5.Number of people who spent more than 2,000.00 who are from NY 

6.Number of people who spent more than 4,000.00 who are from NY 

7.Number of people who bought more than 4 items who are from FL 

FXML 

---------------------- 

elements in scene builder is included in java syntax  

Java node<T> 

------------------------ 

Instead of <T>, you can actually write anything and it will work the same way. Try writing <ABC> in place of <T>. 

This is just for convenience: 

<T> is referred to as any type 

<E> as element type 

<N> as number type 

<V> as value 

<K> as key 

But you can name it anything you want, it doesn't really matter. 

Moreover, Integer, String, Boolean etc are wrapper classes of Java which help in checking of types during compilation. For example, in the above code, obj is of type String, so you can't add any other type to it (try obj.add(1), it will cast an error). Similarly, obj1 is of the Integer type, you can't add any other type to it (try obj1.add("hello"), error will be there). 

J shell 

---------------------- 

jshell> Map<String,String> map = new HashMap<>(); 

map ==> {} 

jshell> map.put("symbol","eq:ibm-1") 

$2 ==> null 

jshell> map 

map ==> {symbol=eq:ibm-1} 

jshell> map.put("price","gt:45") 

$4 ==> null 

jshell> map 

map ==> {symbol=eq:ibm-1, price=gt:45} 

jshell> map.get("symbol") 

$6 ==> "eq:ibm-1" 

jshell> map.get("price") 

$7 ==> "gt:45" 

jshell> String data = map.get("price") 

data ==> "gt:45" 

jshell> data.split(":") 

$9 ==> String[2] { "gt", "45" } 

J shell P2 

---------------------- 

HashMap states = new HashMap(); 

states.put(“NY”,.10); 

states.put(“CT”,.04); 

states.put(“FL”,.06); 

states.put(“PA”,.07); 

states 

states.get(“NY”) 

try might include terminal 

-------------------------------------- 

Save the file as MyPackageClass.java, and compile it: 

C:\Users\Your Name>javac MyPackageClass.java 

Then compile the package: 

C:\Users\Your Name>javac -d . MyPackageClass.java 

To run the MyPackageClass.java file, write the following: 

C:\Users\Your Name>java mypack.MyPackageClass