 Bits is short for binary digit and is a fundamental base unit of info that alternate from 0 to 1 also known as binary numbers  
  
Bits = 1 or 0 > 10 is 2 bits at max it can be 8 bits > 10100011  
Byte converts to 8 bits = 10100011 > Byte can represent 0 to 256  
  
Binary format:  
1 = 00000001  
2 = 00000010  
3 = 00000011  
4 = 00000100  
  
In notes look at base 2  
  
  
  
  
I Fixed-Width Integer  
  
An integer represented by a fixed amount of bits. For example a 32-bit integer is an integer represented by 32 bits (4 bytes) and a 64-bit integer is an integer represented by 64 bits (bytes)  
  
The following is the 32-bit representation of the number 1, with dearly separated  
  
bytes:  
00000000 00000000 00000000 00000001  
  
  
The following is the 32-bit representation of the number 1, with dearly separated  
  
bytes:  
  
00000000 00000000 00000000 00000000 00000000 00000000 00000000 00001010  
  
  
Regardless of how large an integer is, its fired width-integer representation is by definition, made up of a constant number of bits  
  
It follows that, regardless of how large an integer is an operation performed on its fixed-width integer representation consists of a constant number of bit manipulations, since the integer is made up of a fixed number of bits  
  
  
  
Memory  
  
Broadly speaking, memory is the foundational layer of computing where all data is stored.  
  
In the context of coding interviews, its important to note the following points:  
  
Data stored in memory is stored in bytes and by extension, bits  
  
Bytes in memory can "point to other bytes in memory, so as to store references to other data  
  
The amount of memory that a machine has is bounded making it valuable to limit how much memory an algorithm takes up  
  
Accessing a byte or a fixed number of bytes (like 4 bytes or 8 bytes in the case of 32-bit and 64-bit integers) is an elementary operation, which can be loosely treated as a single unit of operational work