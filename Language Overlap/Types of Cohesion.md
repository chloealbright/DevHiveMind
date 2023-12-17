---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates: "[[Coupling vs Cohesion]]"
---
## Best to Worst 

### Functional Cohesion 

The execution of the task related to the problem is the only concern from all the elements inside the module. 

The purpose of functional cohesion is single minded, strong and focused. 

All the elements in the module perform only the necessary activities. 

Some of the examples of functional cohesion are read transaction record, cosine angle computation, seat assignment to an airline passenger etc. 

### Sequential Cohesion 

The data which is the output of one activity is used an input data for the next activity, the involvement of elements is as such. 

Sequential cohesion is easy maintenance and provides a good coupling. 

Sequential cohesion cannot be reused readily because of the activities that are not useful even when used together. 

Some of the examples of sequential cohesion are cross validate record and formatting of module, raw records usage, formatting of raw records, cross validation of fields in raw records, returning of formatted cross validated records. 

### Communicational Cohesion 

The activities using the same input data or output data are contributed by the elements inside the module. 

Communicational cohesion is not flexible like we can only focus on some of the activities and not others at once. 

Communicational cohesion consists of the links because of which the activities affect each other. 

The cohesive ones that are functional are split by communicational cohesion. 

Some of the examples of communicational cohesion are customer details determining modules, usage of customer account number, finding the name of the customer, finding the loan balance of the customer, returning loan balance and the name of the customer etc. 

### Procedural Cohesion 

The activities are related if the elements in the module are related by sequence, otherwise they are not related. 

Procedural cohesion and sequential cohesion are like each other except that the elements in the module of procedural cohesion are not related. 

Procedural cohesion is found at the top of the hierarchy like the module of main program. 

Some of the examples of procedural cohesion are read, write, edit of the module, record use out, writing out the record, reading the record, zero padding to the numeric fields, returning records etc. 

### Temporal Cohesion 

The activities related in time consists of elements from the module. 

Temporal cohesion is found in the modules of initialization and termination. 

The module cannot be reused because the elements in the module are not related to each other. 

The best practice in temporal cohesion is to terminate as early as possible and initialize as late as possible. 

Some of the examples of temporal cohesion are initialization of module, setting the counter to zero, opening the student file, clearing the variables of error message, initializing the array etc. 

### Logical Cohesion 

The activities of the same type or same general category is contributed by the elements in the module. 

Examples of activities of the same type or same general category being contributed by the elements in the module include a report module, display module or input/output module. 

Logical cohesion consists of control coupling as one of the activities will be selected. 

Some of the examples of logical cohesion are module for displaying record as below: 

Use type of the record as record. 

If type of the record is student. then, 

Display the record from student. 

Else if the type of the record is staff, then 

Display the record from staff. 

### Coincidental Cohesion 

The activities with meaningless relationship with one another are contributed by the elements in the module. 

Coincidental cohesion and logical cohesion are like each other except that the activities will be of different types. 

Coincidental cohesion consists combination of activities like rojak. 

Understanding and maintenance of Coincidental cohesion is difficult and there are possibilities of side effects whenever there is modification in the module. 

Some of the examples of coincidental cohesion are module for miscellaneous functions, customer record usage, displaying of customer record, calculation of total sales, reading the transaction record etc. 

### Cohesion 

Cohesion is a measure that defines the degree of intra-dependability within elements of a  module. The greater the cohesion, the better is the program design. There are seven types of cohesion, namely –  

[http://pages.cpsc.ucalgary.ca/~eberly/Courses/CPSC333/Lectures/Design/cohesion.html](http://pages.cpsc.ucalgary.ca/~eberly/Courses/CPSC333/Lectures/Design/cohesion.html) 

## Advantages of Cohesion is Software Engineering 

#### Below are the advantages using Cohesion is Software Engineering: 

The complexity of the modules can be reduced using cohesion in software engineering. The modules can be made simpler consisting of very few operations using cohesion in software engineering. 

The maintainability of the system can be increased using cohesion in software engineering because whenever there are logical changes in the domain, only fewer modules are affected and change in one module cause very few changes in other modules. 

Cohesion in software engineering has a balance between both unit complexity and coupling because a perfect cohesion is possible in a module if only it consists of single element that is atomic and consisting of only one function. Such module consisting of only one element can be either too complicated in order to be able to achieve the task or can be too narrow while being in tight coupling with other modules. 

The reusability of the modules can be increased by using cohesion in software engineering because the components needed by the developers of the application can be found easily in a cohesive set of operations produced by the module using cohesion in software engineering.