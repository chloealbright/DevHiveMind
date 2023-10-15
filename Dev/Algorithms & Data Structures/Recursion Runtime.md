![[_Files/Algo/GetImage (2).png]]
[https://www.enjoyalgorithms.com/blog/time-complexity-analysis-of-recursion-in-programming](https://www.enjoyalgorithms.com/blog/time-complexity-analysis-of-recursion-in-programming) 

# To know 

Recursive definition: a definition in which an entity is defined in terms of a smaller version of itself. 

Anything that could be done recursively can be done iteratively with a for loop and vice versa 

You can make recursive methods O(n) when you use dynamic programming specifically memiozation 

Recursive methods are readable but can have large stacks 

Some of the situations where you might want to use recursion are When you're searching  

When you are using trees or converting something into trees consider recursion for dividing conquer approach In some cases when it comes to sorting and dynamic programming 

# Ways to implement 

General case (Recursive case): the case in a recursive definition in which the method is calling itself example incrementing through array and passing i++  

Indirectly recursive: a method that calls another method and eventually results in the original method call.               

	function do = ()  =>{  something() }                                                                
	
	function  something = () =>{  something()} 

Direct recursion:   function do = () => do()                           

Tail recursive method: a recursive method in which no statements are executed after the return from the recursive call 

Infinite recursion: the situation in which a function calls itself over and over endlessly. 

All ways setup recursive case/procedure before Base case which is like the iteration condition or if statement acting as the while loop   

# Divide & Conquer (Think merge Sort) 

Step 1 -  can be something like this  

current = printFowardRec(current.next)  

doesn't necessary have to be in a variable always establish first even if it isn't the first step in the code 

Step 2 - the iteration condition is like this  

  while(current!== null) change to  if(current!== null) 

Step 3 - contains other steps in this order 

      Step 2 -  if(current!== null) return 

else run base   

       Step 1 -  current = printFowardRec(current.next)  

With all the steps recurrence relation is happening 

 A recurrence relation is an equation that defines a sequence based on a rule that gives the next term as a function of the previous term(s). for some function factorial.  

try assuming simpler smaller cases  so maybe do something like fact 2 visualize things draw tree structure to debug recursion compare harder case to simpler case then generate base case 

factorial 4 

	fact(4) = n * fact(n-1) 
	
	fact(1) = 1 
	
	fact(2) = 1  * fact(1)   
	
	and so on  4 * 3 * 2 * 1 
	
fact(4) = 4  * fact(3)  would be start if going down to 1 
	
		Step 1 - return n * fact(n-1) 
		
		Step 2 - stop condition  if n === 1 return 1 
		
		logic/answer




## Optimize & Solve Technique: Base Case and Build   

With Base Case and Build, we solve the problem first for a base case (e.g., n   = 1) and then try to build up from there. When we get to more complex/interesting cases (often n = 3 or n = 4), we try to build those using the prior solutions.  

Example: Design an algorithm to print all permutations of a string. For simplicity, assume all characters are unique.   

Consider a test string abcdefg.   

Case "a"--> {"a"}  

Case "ab" - -> {"ab", "ba"}   

Case "abc" --> ?   

This is the first "interesting" case. If we had the answer to P ("ab"), how could we generate P ("abc")? Well, the additional letter is "c," so we can just stick c in at every possible point. That is:   

P("abc") = insert "c" into all locations of all strings in P("ab")   

P("abc") = insert "c" into all locations of all strings in {"ab","ba"}   

P("abc") = merge({"cab", ""acb", "abc"},  {"cba", abca", bac"})  

P("abc") = {"cab", "acb", "abc", "cba", "bca", bac"}   

Now that we understand the pattern, we can develop a general recursive algorithm. We generate all permutations of a string s_1 ••• s_n by "chopping off" the last character and generating all permutations of s_1 •••s_n-1. Once we have the list of all permutations of s_1 ••• s_n-1, we iterate through this list. For each string in it, we insert Sn into every location of the string. Base Case and Build algorithms often lead to natural recursive algorithms.