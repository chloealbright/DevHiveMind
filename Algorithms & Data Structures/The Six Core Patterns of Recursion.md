---
tags:
  - looping
author: jacgit18
---
![[unnamed (55).gif]]

## Iteration 

As you may know, any problem that can be solved using loops can also be solved using recursion in place of it and vice-versa. It may not come handy often, but can be useful once in a while. We can use this pattern when we refer back to the items we’ve looped through previously. 

## Subproblems 

One of the core reasons why recursion is used is that it lets us break down the problems into its subproblems. If you look closely, you could use this to solve any recursive problem, but we are going through the other patterns because they get much more specific about helping you do that. 

You must have come across problems that themselves are speaking to be broken down into subproblems. One such example is the Fibonacci problem. In this case, even the mathematical definition of the Fibonacci sequence is recursive in nature. 

Another problem that frequently comes up is the Towers of Hanoi problem. In problems like this, you have to come up with the decision of breaking down the problem into its subproblems. 

## Selection 

It is the most common pattern to come up in Recursion and Dynamic Programming. In this pattern, we are going through all the possible solutions and selecting the ones which match our condition. 

Let’s consider the example of the 0–1 Knapsack Problem. In this problem, we have a series of weights associated with some value. We have to figure out the maximum value that we can achieve under some specific weight. This problem is a classic dynamic programming problem, but let’s look at it from a recursive approach. 

The brute force solution to this problem is to generate all the possible combinations and choose the most optimal answer from it. 

List<List<Integer>> combinations(int[] n) {            

List<List<Integer>> results = new LinkedList();                            

combinations(n, 0, results, new LinkedList<Integer>());               

 return results;                                                                                                

          } 

void combinations(int[] n, int i, List<List<Integer>> results, List<Integer> path){                                                                                         

        if (i == n.length) {        

              results.add(path);        

            return;                           

    } 

   // Find all the combinations that exclude the current item 

   // Find all the combinations that include the current item 

 List<Integer> pathWithCurrent = new LinkedList(path);  

pathWithCurrent.add(n[i]);                                                               

combinations(n, i+1, results, path);                                                         

combinations(n, i+1, results, pathWithCurrent);                          

                     } 

## Ordering 

This pattern is the permutation to Selections’ combination. We’re focused on the case where we are concerned about the different ordering of the values. Figure out all the permutations of a given set of elements is the most straightforward problem. 

Some examples are Bogosort (generate all the permutations and then determining which is sorted), or determining all palindromes from a set of characters. 

List<List<Integer>> permutations(Set<Integer> n) {                                                           

  List<List<Integer>> results = new LinkedList();                          

   permutations(n, results, new LinkedList<Integer>());                               

      return results;                                                                                                   

       } 

void permutations(Set<Integer> n, List<List<Integer>> results, List<Integer> path) {                                                                              

      if (n.isEmpty()) {                                                                            

    results.add(path);                                                                                       

     return;                                                                                                                 

         } 

// For now ignore concurrent modification issue                

             for (int i : n) {                                                                              

       n.remove(i);                                                                         

                List<Integer> pathWithCurrent = new LinkedList(path);       

pathWithCurrent.add(i);                                               

               permutations(n, results, pathWithCurrent);           

n.add(i);                                                                                                                              }                                                                                                                                  } 

## Divide and Conquer 

In divide and conquer, we split the space into half, solve each help separately, and then combine them to get the result. Divide and conquer is the core of many algorithms such as merge sort, depth-first search, and binary search. 

This technique is an approach to tree and sorting/searching problems where we split the problem space and then recombine the results to get the final solution. 

The code to split a string into its every point: 

List<String> parentheses(String s) {                             

                  if (s.length() == 1) {                                                                           

        List<String> result = new LinkedList<String>();                           

     result.add(s);                                                                                         

         return result;                                                                                           

                   } 

List<String> results = new LinkedList<String>();                         

                       for (int i = 1; i < s.length(); i++) {                                     

                    List<String> left = parentheses(s.substring(0, i));                                    List<String> right = parentheses(s.substring(i, s.length()));                  

             for (String s1 : left) {                                                                        

                          for (String s2 : right) {                                                              

            results.add("(" + s1 + s2 + ")");                                  

                                              } 

 }                                                           

                                                                }                                                                                                                    return results; 

DFS 

DFS is the final pattern that our recursive functions can fall. It is also widely used because DFS (or BFS) is used almost whenever working with trees and graphs. 

A critical thing with DFS is not limiting yourself to searching the nodes in a tree or graphs but also knowing how to find the path itself.