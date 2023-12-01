---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### Optimize & Solving Technique #1: DIY (Do It Yourself)  
like if you comparing strings expand the variables or prams to something bigger to make it easier then scale down to the specific problem  

### Optimize & Solve Technique #2: Simplify and Generalize  
With Simplify and Generalize, we implement a multi-step approach. First we simplify or tweak some constraint, such as the data type. Then, we solve this new simplified version of the problem. Finally, once we have an algorithm for the simplified problem, we try to adapt it for the more complex version.  

### Optimize & Solve Technique #3: Base Case and Build  
With Base Case and Build, we solve the problem first for a base case (e.g., n = 1) and then try to build up from there. When we get to more complex/interesting cases (often n = 3 or n = 4), we try to build those using the prior solutions.  

Example: Design an algorithm to print all permutations of a string. For simplicity, assume all characters are unique.  

### Consider a test string abcdefg.  
	Case "a"--> {"a"}  
	Case "ab" - -> {"ab", "ba"}  
	Case "abc" --> ?  
This is the first "interesting" case. If we had the answer to P ("ab"), how could we generate P ("abc")? Well, the additional letter is "c," so we can just stick c in at every possible point. That is:  
	P("abc") = insert "c" into all locations of all strings in P("ab")  
	P("abc") = insert "c" into all locations of all strings in {"ab","ba"}  
	P("abc") = merge({"cab", ""acb", "abc"}, {"cba", abca", bac"})  
	P("abc") = {"cab", "acb", "abc", "cba", "bca", bac"}  
Now that we understand the pattern, we can develop a general recursive algorithm. We generate all permutations of a string s_1 ••• s_n by "chopping off" the last character and generating all permutations of s_1 •••s_n-1. Once we have the list of all permutations of s_1 ••• s_n-1, we iterate through this list. For each string in it, we insert Sn into every location of the string. Base Case and Build algorithms often lead to natural recursive algorithms.  

### Optimize & Solve Technique #5: Data Structure Brainstorm  
This approach is certainly hacky, but it often works. We can simply run through a list of data structures and try to apply each one. This approach is useful because solving a problem may be trivial once it occurs to us to use, say, a tree.  

Example: Numbers are randomly generated and stored into an (expanding) array. How would you keep track of the median?  

Our data structure brainstorm might look like the following:  
	Linked list? Probably not. Linked lists tend not to do very well with accessing and sorting numbers.  
	
Array? Maybe, but you already have an array. Could you somehow keep the elements sorted? That's probably expensive. Let's hold off on this and return to it if it's needed.  

Binary tree? This is possible, since binary trees do fairly well with ordering. In fact, if the binary search tree is perfectly balanced, the top might be the median. But, be careful-if there's an even number of elements, the median is actually the average of the middle two elements. The middle two elements can't both be at the top. This is probably a workable algorithm, but let's come back to it.  

Heap? A heap is really good at basic ordering and keeping track of max and mins. This is actually interesting-if you had two heaps, you could keep track of the bigger half and the smaller half of the elements. The bigger half is kept in a min heap, such that the smallest element in the bigger half is at the root. The smaller half is kept in a max heap, such that the biggest element of the smaller half is at the root. Now, with these data structures, you have the potential median elements at the roots. If the heaps are no longer the same size, you can quickly "re-balance" the heaps by popping an element off the one heap and pushing it onto the other.  


## When you’re stuck on getting started  
1) Write a sample input on the whiteboard and turn it into the correct output "by hand." Notice the process you use. Look for patterns, and think about how to implement your process in code.  

	Trying to reverse a string? Write “hello” on the board. Reverse it “by hand”—draw arrows from each character’s current position to its desired position.  

	Notice the pattern: it looks like we’re swapping pairs(potentially map) of characters, starting from the outside and moving in. Now we’re halfway to an algorithm.  

2) Solve a simpler version of the problem. Remove or simplify one of the requirements of the problem. Once you have a solution, see if you can adapt that approach for the original question.  
	Trying to find the k-largest element in a set? Walk through finding the largest element, then the second largest, then the third largest. Generalizing from there to find the k-largest isn’t so bad.  
	
3) Start with an inefficient solution. Even if it feels stupidly inefficient, it’s often helpful to start with something that’ll return the right answer. From there, you just have to optimize your solution. Explain to your interviewer that this is only your first idea, and that you suspect there are faster solutions.  
	Suppose you were given two lists of sorted numbers and asked to find the median of both lists combined. It’s messy, but you could simply:  
		Concatenate the arrays together into a new array.  
		Sort the new array.  
		Return the value at the middle index.  
		
### When you’re stuck on finding optimizations  
1) Look for repeat work. If your current solution goes through the same data multiple times, you’re doing unnecessary repeat work. See if you can save time by looking through the data just once.  
	Say that inside one of your loops, there’s a brute-force operation to find an element in an array. You’re repeatedly looking through items that you don’t have to. Instead, you could convert the array to a lookup table to dramatically improve your runtime.  
	
2) Look for hints in the specifics of the problem. Is the input array sorted? Is the binary tree balanced? Details like this can carry huge hints about the solution. If it didn’t matter, your interviewer wouldn’t have brought it up. It’s a strong sign that the best solution to the problem exploits it.  

	Suppose you’re asked to find the first occurrence of a number in a sorted array. The fact that the array is sorted is a strong hint—take advantage of that fact by using a binary search.  

	Sometimes interviewers leave the question deliberately vague because they want you to ask questions to unearth these important tidbits of context. So ask some questions at the beginning of the problem.  
	
3) Throw some data structures at the problem. Can you save time by using the fast lookups of a hash table? Can you express the relationships between data points as a graph? Look at the requirements of the problem and ask yourself if there’s a data structure that has those properties.  

4) Establish bounds on space and runtime. Think out loud about the parameters of the problem. Try to get a sense for how fast your algorithm could possibly be:  

	“I have to at least look at all the items, so I can’t do better than O(n)O(n) ↴ time”.  
	
	“The brute force approach is to test all possibilities, which is  
	
	O(n^2)O(n 2) time. So the question is whether or not I can beat that time.”  

	“The answer will contain n^2n 2  

	items, so I must at least spend that amount of time.”  

### When All Else Fails  
1) Make it clear where you are. State what you know, what you’re trying to do, and highlight the gap between the two. The clearer you are in expressing exactly where you’re stuck, the easier it is for your interviewer to help you.  

2) Pay attention to your interviewer. If she asks a question about something you just said, there’s probably a hint buried in there. Don’t worry about losing your train of thought—drop what you’re doing and dig into her question.  

	Relax. You’re supposed to get stuck.  
	
	Interviewers choose hard problems on purpose. They want to see how you poke at a problem you don’t immediately know how to solve.  
	
	Seriously. If you don’t get stuck and just breeze through the problem, your interviewer’s evaluation might just say “Didn’t get a good read on candidate’s problem-solving process—maybe she’d already seen this interview question before?”  
	
	On the other hand, if you do get stuck, use one of these tricks to get unstuck, and communicate clearly with your interviewer throughout...that’s how you get an evaluation like, “Great problem-solving skills. Hire.”