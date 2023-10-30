---
tags:
  - python
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---


phrase = "hello world!"  // no semi colon needed 

White space  needed 

""" A multi-line comment in Python. Can also be used to create multi-line 

    string literals, which can be assigned to variables. """ 

A single-line comment in Python 

## Comparisons 

==  ,  !=  ,  >  ,  <  ,  <=  and  >=  are used to compare values: 

some_variable[0] == 'blah' 

is and is not are used to compare identities: 

some_variable is list 

## Iterable objects 

If an object is iterable, you can simply use the  for ... in  pattern: 

iterable_list = [1, 2, 3]  

for item in iterable_list:     number_of_items += 1  

## Using set ranges 

You can specify a set range to iterate over. The loop iterates three times (0 to 2) in the example below. 

for i in range(0, 3): number_of_iterations += 1  

In the above example, you can use 'i' as the index variable name (e.g., the index when iterating over a list). 

## Generating ranges for use in for loops 

The following defines a range using the length of a string (which is not iterable by itself since it's an int). The below is equivalent to a for (var i = 0; i < some_length; i++)  pattern that you might use in other languages. 

for i in range(0, len('hello')):     number_of_iterations += 1  

## While Loops 

The following is how you write while loops: 

while True:     count_to_infinity += 1  

## Finding length of strings 

length_of_string = len('hello')  # length_of_string == 5  

## Checking character type 

The following returns true for strings of length >= 1. 

some_string.isalnum()  # Returns True if entire string is alphanumeric  

some_string.isalpha()  # Returns True if entire string is alphabetic  

some_string.isdigit()  # Returns True if entire string consists of digits  

some_string.isspace()  # Returns True if string contains only whitespaces  

## Checking for substring 

'hello' in 'hello world'  # Returns True, since 'hello' is in 'hello world'  

'hello' not in 'hello world'  # Returns False  

## Splitting 

'1::2'.split(':')  # Returns ['1', '', '2'])  

## Joining 

' bar '.join(['foo', 'baz'])  # Returns 'foo bar baz'  

## Slicing 

some_string = "hello world"  

some_string[1]    # 'e'  

some_string[1:2]  # 'e'  

some_string[1:1]  # ''  

some_string[4:7]  # 'o w'  

some_string[4:]   # 'o world'  

some_string[:7]   # 'hello w'  

some_string[-3:]  # 'rld'  

some_string[:-3]  # 'hello wo'  

## Splicing 

Because Python strings are immutable, there is no splice method for strings. You can, however, do this: 

string1 = "foo bar baz" string2 = string1[:4] + 'qux' + string1[7:]  # 'foo qux baz'  

## Lists (Variable-Length Arrays) 

Python lists may be referred to as variable-length arrays in other languages. The following lists basic actions you can perform on a list. 

### Declaring 

example_list = ['apples', 'oranges', 42]  

### Appending 

example_list.append('hello world')  

### Inserting 

example_list.insert(2, 'answer')  # Inserts 'answer' at position 2  

### Popping 

last_item = example_list.pop()   # Removes and returns last item on list item_at_2 = example_list.pop(2)  # Removes and returns item at position 2  

### Reversing a list 

example_list.reverse()  # In-place reversal (modifies example_list)  

### Returning list length 

len(example_list)  


### Deleting 

del example_list[1]  # Deletes item at index 1 (del reduces list length)  

del example_list[1:2]  # Deletes items from index 1 to index 2  

del example_list[:]  # Deletes everything from list (list now zero length)  


### Dictionaries (Associative Arrays) 

Python dictionaries may be referred to as associative arrays in other languages. The following lists basic actions you can perform on a dictionary. 


### Declaring 

size_abbreviations = {'small': 'S', 'medium': 'M', 'large': 'L'}  



### Returning values 

my_size = size_abbreviations['medium']  # Returns 'M'  


### Adding / assigning values to elements 

size_abbreviations['extra large'] = 'XL'  # Adds this element to dictionary  


### Removing elements 

del size_abbreviations['medium'] # Removes 'medium':'M' pair from dictionary  

### Sets 

The following lists basic actions you can perform on a set. 


### Constructor 

a_set = set()  # Creates an empty set  


### Adding to a set 

a_set.add('hello')  


### Removing from a set 

a_set.remove('hello')  


### Clearing a set 
a_set.clear()  # Removes all elements from the set  


### Creating a set from a list 
set_from_list = set(['apples', 'oranges'])  


### Checking for items in a set 
if 'apples' in set_from_list: return('yes, we have apples!') if 'pineapple' not in set_from_list: return('but no pineapples for you!')