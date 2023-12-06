Now that we know a different kind of keys in DBMS, let’s see how to identify them when given a table from a database. For this, we use the concept of functional dependencies.

![[Functional Dependencies.png]]

A ***functional dependency (FD)*** is a constraint between two sets of attributes. This constraint is for any two tuples t1 and t2 in r if t1[X] = t2[X], then they have t1[Y] = t2[Y]. This means the value of the X component of a tuple uniquely determines the value of component Y.  

FD is denoted as X ? Y (this is read as “Y is functionally dependent on X”). The left side is called the determinant, and the right side is called the dependent. 

## Closure of a set of Attributes 

A <mark style="background: #FFF3A3A6;">closure</mark> is a set of all possible FDs derived from a given set of FDs. It is also referred to as a <mark style="background: #FFF3A3A6;">complete</mark> set of FDs. If F is used to donate the set of FDs for relation R, then the closure of a set of FDs implied by F is denoted by F+. 

We will now define the closure of a set of attributes concerning a given set of FDs. It will help<mark style="background: #FFF3A3A6;"> identify the super Key</mark> of the relationship and find whether an FD can be inferred from a given set of FDs or an FD is redundant. After finding a set of functional dependencies on a relation, the next step is to find the Super Key for that relation (table). 

Then we find out the set of attributes’ closure to decide whether an attribute (or set of attributes) of any table is a key for that table or not. The <mark style="background: #FFF3A3A6;">set of attributes </mark>that are functionally dependent on the attribute X is called Attribute Closure of X, and it can be represented as X+. 

Below are some rules needed to determine F+: 

1.  Reflexivity: If X is a superset of Y or Y is a subset of X, then X ? Y. 
    
2.  Augmentation: If X ? Y, then XZ ? YZ. Or If Z ⊆W, and X ? Y, then XW ? YZ. 
    
3.  Transitivity: If X ? Y and Y ? Z, then X ? Z. 
    
4.  Union: If X ? Y and X ? Z, then X ? YZ. 
    
5.  Decomposition: If X ? YZ, then X ? Y and X ? Z. 
    
6.  Pseudo-Transitivity: If X ? Y and YW ? Z, then XW ? Z.