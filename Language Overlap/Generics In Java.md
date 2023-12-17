---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Used to reduce multiple duplicates of classes that may be the same but of different data types like String, Integer, or Double

//lets you use any type

Public class Printer <T>{

T thingsToPrint

public Printer(T thingsToPrint ){

this.thingsToPrint = thingsToPrint;

}

public void print(){

SyOut.println(thingsToPrint)

}

}

Integer,Double, String are wrappers for primitive types

Printer <Integer> printer = new Printer <> (23);

printer.print()

Printer <Double> printer = new Printer <> (23);

Printer <Cat> cats = new ArrayList <> ();

not compatible with primitive types

when you create a new instance of class you just pass in the type

[https://www.youtube.com/watch?v=K1iu1kXkVoA&list=WL&index=5&ab_channel=CodingwithJohn](https://www.youtube.com/watch?v=K1iu1kXkVoA&list=WL&index=5&ab_channel=CodingwithJohn)