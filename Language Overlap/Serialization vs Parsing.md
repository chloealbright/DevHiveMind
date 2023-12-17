---
tags:
  - review
  - CombinePart2
  - Serialization
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
Serialization is the process of translating data structures or objects states into format that can be stored or transmitted and reconstructed later possibly in a different computer environment



Serialization  = encoding is the process of converting a data structure into a format that it can be safely stored or transmitted and the recreated from the stored or transmitted format. It's usually used to refer to applying this process to complex data structures like trees, objects, or graphs, as they don't inherently lend themselves to being transmitted as a simple string of binary data. Converting an in-memory object to JSON or XML is an example of serialization. 



Serializable basically is a string on an array that is irritable and is converted to be deserialized which is to convert that array into an object 

Deserialization = decoding = parsing is the opposite process, of taking a text format and building a data structure. The difference to parsing is that when deserializing, your data is still formatted. You expect this text format to adhere to a standard. When parsing, you are writing logic to turn one format of input into another, deserialization in my understanding is more just exchanging between alternate representations of the same data format. 

Parsing, on the other hand, takes a stream of (structured) data and then does something based on the contents of that stream, usually either creating an in-memory structure based on it, or executing a sequence of operations based on it. Deserialization (the reverse process of serialization) is a particular type of parsing, it takes serialized data and recreates the original data structure from it. However, you can do many other types of parsing. Compiling source code is also a type of parsing (together with then serializing the result of the parsing as machine code or assembly), as is linting or formatting code, doing static analysis of it, and many other things you would do to it using tools. So is decompressing a compressed file or listing the contents of an archive. 

Note that both terms are very generic. Parsing routines and data serialization routines tend to be rather specific to the exact purpose they were designed for. 

In computers, encoding is the process of putting a sequence of characters (letters, numbers, punctuation, and certain symbols) into a specialized format for efficient transmission or storage. ... (We can encrypt data without changing the code or encode data without deliberately concealing the content.)



Communication messages structure refers to the organization of data within messages exchanged between different components or systems. This structure often includes fields, headers, and other metadata that convey information. Schema registries, on the other hand, are systems or services that manage the schemas associated with the serialized data. They store the structure or schema definitions, allowing systems to understand how to interpret serialized messages.

Now, let's delve into the serialization formats you mentioned:

1. **Avro:**
   - **Pros:**
     - Compact binary format.
     - Supports schema evolution, allowing changes to the schema over time.
     - Integration with schema registries for centralized schema management.
   - **Cons:**
     - May not be as fast as some other binary formats.

2. **Protocol Buffers (protobuf):**
   - **Pros:**
     - Efficient binary serialization.
     - Well-defined schema using Protocol Buffer Language.
     - Compact size and high performance.
   - **Cons:**
     - Lack of support for schema evolution can be a limitation.

3. **Thrift:**
   - **Pros:**
     - Binary format with a focus on performance.
     - Code generation for multiple languages.
     - Supports schema evolution.
   - **Cons:**
     - Requires additional dependencies for some languages.

**Communication Message Structure:**
- Messages typically consist of fields, each with a defined data type.
- Headers may contain metadata like message type, version, or routing information.
- Schemas define the structure of messages, ensuring consistency.

**Schema Registries:**
- They centralize schema management for serialized data.
- Enable versioning and evolution of schemas.
- Systems can fetch schemas from the registry to interpret serialized messages correctly.

In summary, Avro, protobuf, and Thrift are popular for their binary nature and schema support. The choice depends on factors like performance, schema evolution requirements, and language support. Schema registries play a crucial role in maintaining and versioning schemas, facilitating interoperability in distributed systems.