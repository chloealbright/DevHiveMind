---
tags:
  - review
  - CombinePart2
  - Serialization
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
Serialization  = encoding is the process of converting a data structure into a format that it can be safely stored or transmitted and the recreated from the stored or transmitted format. It's usually used to refer to applying this process to complex data structures like trees, objects, or graphs, as they don't inherently lend themselves to being transmitted as a simple string of binary data. Converting an in-memory object to JSON or XML is an example of serialization. 

Serializable basically is a string on an array that is irritable and is converted to be deserialized which is to convert that array into an object 

Deserialization = decoding = parsing is the opposite process, of taking a text format and building a data structure. The difference to parsing is that when deserializing, your data is still formatted. You expect this text format to adhere to a standard. When parsing, you are writing logic to turn one format of input into another, deserialization in my understanding is more just exchanging between alternate representations of the same data format. 

Parsing, on the other hand, takes a stream of (structured) data and then does something based on the contents of that stream, usually either creating an in-memory structure based on it, or executing a sequence of operations based on it. Deserialization (the reverse process of serialization) is a particular type of parsing, it takes serialized data and recreates the original data structure from it. However, you can do many other types of parsing. Compiling source code is also a type of parsing (together with then serializing the result of the parsing as machine code or assembly), as is linting or formatting code, doing static analysis of it, and many other things you would do to it using tools. So is decompressing a compressed file or listing the contents of an archive. 

Note that both terms are very generic. Parsing routines and data serialization routines tend to be rather specific to the exact purpose they were designed for. 

In computers, encoding is the process of putting a sequence of characters (letters, numbers, punctuation, and certain symbols) into a specialized format for efficient transmission or storage. ... (We can encrypt data without changing the code or encode data without deliberately concealing the content.)