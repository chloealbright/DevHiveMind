![[_Files/Algo/unnamed (4).gif]]

Runtime can range from Worst, Average, & Best(for sorting algorithm) Case  

Scale Descending from EXCELLENT to WORST TIME 

# Calculating runtime of algorithm ex: 

	When you have an advance algorithm with multiple parts with different runtimes like on giant function the overall runtime calculates down by this: 

<mark style="background: #FFF3A3A6;">higher WORST runtime  + lower EXCELLENT runtime = higher WORST runtime  </mark>

		O(n) + O(n log(n)) = O(n log(n)) 
	
		which ends up being O(n log(n))) since it is trending up towards worst time 

	For Big O complexity, all you care about is the dominant term. n log(n) dominates n so that's the only term that you care about. 

Big O notation describes the asymptotic behavior of functions. Basically, it tells you how fast a function grows or declines. 

Informally, the term asymptotic means approaching a value or curve arbitrarily closely 

	O represents Upper bound or worst case O(n) also known as Landau's symbol which comes from the name of the German number theoretician Edmund Landau who invented the notation. The letter O is used because the rate of growth of a function is also called its order. 
	
	Ω represents lower bound or best case Ω(n) also is called the Omega sign which represents the time of end or end of the world 
	
	Θ represents any other case besides worst and best O(n) also it's called theta sign which refers to the rate of decline in the value of an option due to the passage of time. It can also be referred to as the time decay of an option. This means an option loses value as time moves closer to its maturity, as long as everything is held constant. 

https://cs.stackexchange.com/questions/57/how-does-one-know-which-notation-of-time-complexity-analysis-to-use 

# Things that increase runtime in a function 

	Operations (+, -, *, /) 
	
	Comparisons (<, >, ==) 
	
	Looping (for, while)
	
	Outside Function call (function()) 
	
	Recursion Function call 

![[Runtime Big O.png]]

RUNTIMES(Assume worst case is within EXCELLENT to WORST TIME RANGE) 

FAST RATE OF GROWTH 

Besides that, there is <mark style="background: #FFF3A3A6;">CONSTANT TIME</mark> basically a calculation like 5+5 where there is no data processed or just no loops another example of constant time is when you loop through a print statement it is still considered the constant time or <mark style="background: #FFF3A3A6;">O(1)</mark> One more example let's say you have a function that takes in an array of boxes when it takes in an element it only does one thing meaning as the number of operations scale we maintain constant time, <mark style="background: #FFF3A3A6;">O(1)</mark> is considered an <mark style="background: #FFF3A3A6;">EXCELLENT</mark> algorithm since we don’t need to worry about the input size. examples merge, quick, and heap sort and other sorts also let's say console log the first two index of the array in your function it is considered two operations so it will be <mark style="background: #FFF3A3A6;">O(2)</mark> but will still be <mark style="background: #FFF3A3A6;">CONSTANT TIME O(1)</mark> is just a number we run down two because operation tends to increase but as long as <mark style="background: #FFF3A3A6;">CONSTANT TIME</mark> is there we say <mark style="background: #FFF3A3A6;">O(1)</mark>  

<mark style="background: #BBFABBA6;">CONSTANT TIME if no looping</mark>    

	O(1) when not creating new data 

	O(1) can also be for an object lookup 

Then we have O(log n) LOGARITHMIC TIME like binary search where you reduce iteration time half the array each time until you find what you're looking for this is considered GOOD TIME you can think of this as going through a dictionary book that is a large sorted data set trying to find a word under S and reducing the time by going to S. 

LOGARITHMIC TIME O(log n) if using a binary search or some sort of divide and conquer search or multiplication  

for (i=1; i<=n; i = i*2) { 

    console.log(i); // 1 

  } 

O(n) is the worst-case where n is the number of elements in the array also known as LINEAR TIME complexity where if the array size is increasing the longer it takes to loop through it O(n) is considered FAIR. Basically, anything that uses a loop 

LINEAR TIME O(n) if one loop 

Find max element in an unsorted array,                                                                  

Duplicate elements in an array with Hash Map 

O(n log(n))  LINEARITITHMIC TIME - usually sorting operations 

if sorting or searching is involved  assume LINEARITITHMIC TIME O(n log(n)) merge and quick  sort 

For O(n^2)- QUADRATIC TIME which is HORRIBLE/Worst you can think of it like for each element in your array it squares the next element increasing time complexity also for nested for loop it can also be O(n^2) depending on what you're looping through so pay attention because if your looping through two different arrays in a nest for loop the first array being in the outer loop and the other in the inner then it is considered O(n *m).  But if you're using for loops that are not nested one after another it would be O(n + m) depending on what's your looping through. but typically we use this when we are comparing every element in a collection needs to be compared to every other element. 

+ for steps in order 

* for nested steps 

if comparing and using nested loop QUADRATIC TIMEO(n^2) 

Duplicate elements in array **(naïve)**,                                                        

Sorting array with bubble sort 

O(2^n) EXPONENTIAL TIME- recursive algorithms that solve a problem of size N 

using recursive calls EXPONENTIAL TIMEO(2^n) especially with tree and graph questions also if you use recursion it changes to O(n) for space complexity because you're adding to the call stack taking up memory. Another example is finding all subsets. 

O(n^3) CUBIC TIME - triple nested loop or  3 variables equation solver 

<mark style="background: #BBFABBA6;"><b>O(n!) FACTORIAL TIME</b>- you are adding a loop for every element SLOW RATE OF GROWTH 
</mark>
Iterating through half a collection is still O(n)  

Two separate collections: O(a * b) 

FACTORIAL TIMEO(n!) factorial like questions 

Factorials (!) are products of every whole number from 1 to n. In other words, take the number and multiply through n to 1.  

For example: If n is 3, then 3! is 3 x 2 x 1 = 6. 

 Find all permutations of a given set/string 

So in the end the reality is that some algorithms best cast would be O(n) and there may not be any way of improving it more 

# Calculating Big O & Rules 

1) Drop the constants:- Since we are trying to do worst-case analysis, We can drop the constants as we only care about the growth rate of the algorithm as input size n increases. Constants are insignificant as compared to the input size. 

For example  constants in O(2n)  notation so this would be just O(n)  the only thing that matter if is linear time, in this case, the only time you should keep constants if you're using quadratic time like O(n^2) or  Exponential like O(2^n) 

 Drop  the Constant Ex: O(2n) will be O(n) 

It is very possible for O(N) code to run faster than 0( 1) code for specific inputs. Big O just describes the rate of increase. For this reason, we drop the constants in runtime. An algorithm that one might have described as 0(2N) is actually O(N).  

2) Drop the non-dominant term:- Dominant term is the term that increases most quickly as the size of the input increases. Similarly, like dropping the constant, We can also remove a non-dominant term, Since non-dominant terms do not play a significant role in the approximation.  talking about "O()" notation 

For example  O (x^2+3x+100+x/2) 

You will drop a lot of the stuff here so 

You will have O(x^2) because let's say you plug in five for x, x^2 would be 25  

3x would be 15 100 will stay the same and x/2 would be some decimal number but 100 would be dominant but with big O we worry about scale 

So we passed 5,000 x^2 would be dominant that we keep so it'll be O(n^2) 

What do you do about an expression such as O ( N2 + N)? That second N isn't exactly a constant. But it's not especially important.  

We already said that we drop constants. Therefore, 0( N2 +  N2) would be O ( N2). If we don't care about that latter N2 term, why would we care about N? We don't. 

    •  O(N2 +  N) becomes O(N2).  

    • O(N +  log N) becomes O(N). 

    • 0(5*2N +  1000N^100) becomes 0(2N). 

We might still have a sum in a runtime. For example, the expressions(82 +  A) cannot be reduced (without-some special knowledge of A and B).  

3) In If-Else, Include the block having maximum complexity:- As mentioned earlier, We are interested in the worst case. So when calculating Big O, we should choose the block having maximum complexity. Essentially test case. 

4) Runtime of loop block = runtime of statement(s) * number of iteration