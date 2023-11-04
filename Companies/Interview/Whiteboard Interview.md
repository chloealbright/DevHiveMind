![[unnamed (57).gif]]
Best Practices and Q&A

Prep  
	Look on Glassdoor, and then checking Reddit and Quora you can also check their employees on LinkedIn and see if you have any mutual connections you can try to connect to find out about the type of interview question  

	Master algorithms to be able to solve within 5 to 15 minute  
## Start ##  
## Code Q&A & Planning 

### ❌ Avoid  
	Don't interrupting your interviewer when they are talking. Usually, if they speak, they are trying to give you hints or steer you in the right direction.  
	
### 🤌 Tactics  
	Be thoughtful with your questions, don't ask too many especially since you have limited time, and make sure your questions aren't too dumb.  

Ask the interviewer to restate the question or repeat the question back at the interviewer this gives you time to think  

Between questions and writing code ask if you can get a minute to think in silence by saying ok interesting can I have a little time to think just limit time keep it like 45-sec shift to another mental tab  

If stuck, think about related problems you have seen before and how they were solved.  

If you have to explain a lot of stuff and steps about your code you should probably change your approach 

## ☝️Tip  
Avoid rewriting pseudocode that is repeating what is already known  

Keep in mind: A lot of interviews ask questions that you won’t be able to fully answer on time. So think: What can I show in order to show that I can do this and I am better than other coders.  

Always get confirmation from the interviewer  

Ask the interviewer what they're doing if there bull shiting enthusiastically  

Be honest about what you don't know and know on the interview but attempt problem first and say you haven't seen a problem like this ... to continue the conversation  

## Approach Process ##  
Talk a little about the Brute force(BASIC NO TEST CASE or SIMPLE) approach  

Then transition into talking about the Naïve approach(which is the building blocks for an optimal solution) or go straight into talking about or coding a Greedy/Optimal approach while whiteboard things out a little and listing things down.  

You don't need to code everything if you can mention there might be a cleaner or better way to make it more readable or optimal by refactoring certain parts you could just describe that 

## Coding Process  
Ask questions to clarify everything because questions are made to be vague so try asking things to understand what variables are needed Clarify all this and to come to an agreement on what the question is asking and what the goal is to solve the problem:  
	Inputs/Outputs  
	Define variable names  
	Scope & limitations of problem  
	Data Structures required, Try to scale down to basic data structures to try to understand problems better  
	Algorithms patterns required  
	If sorting Algorithm is required  
	
Edge case(more can be added later)  
	An edge case typically involves input values that require special handling in an algorithm behind a computer program. As a measure for validating the behavior of computer programs in such cases, unit tests are usually created; they are testing boundary conditions of an algorithm, function, or method. So practice unit test for edge casing that you can use in an interview when writing out the problem and clearing up the problem  
	
Corner case(more can be added later)  
	A corner case is when multiple parameters/Inputs are simultaneously at extreme levels, and the user is put at a corner of the configuration space.  

Test cases(conditional statements more can be added later)  
	In software engineering, a test case is a specification of the inputs, execution conditions, testing procedure, and expected results that define a single test to be executed to achieve a particular software testing objective, such as to exercise a particular program path or to verify compliance with a specific …  
	
Ask if it is ok to code after doing these steps and talk through your steps like say  
	Check did you use all the information the interviewer gave you before and after  
	Ok so I'm gonna initializing a pure function called ...  
	Also ask if certain parts of your code are sufficient enough  
	Ask to run code after reading silently and tell them I don't see any bugs can I run my code
	  
## Algo tip  
Modularize your code from the very beginning. Break up your code into beautiful small pieces that are readable and practice good naming convention, also always write a conditional statement to check what the input is I want to do if it's not the input you expect  
Scan through your code for mistakes as if it was your first time seeing code written by someone else.  

Think about error checks and how you can break this code. Never make assumptions about the input. Assume people are trying to break your code and that Darth Vader is using your function. How will you safeguard it? Always check for false inputs that you don’t want. Here is a trick: Comment in the code, the checks that you want to do… write the function, then tell the interviewer that you would write tests now to make your function fail (but you won't need to actually write the tests).  

Test your code: Check for no params, 0, undefined, null, massive arrays, async code, etc… Ask the interviewer if we can make assumptions about the code. Can you make the answer return an error? Poke holes into your solution. Are you repeating yourself?  

Mention removing substring to improve runtime complexity  

Some condition makes sense to have before loop to avoid looping  

You can recursion and nest it in for loop  

You can ask to use regex or general documentation for syntax since some methods take more parameters than you think  

Use map over for each method for your array  

Avoid modifying objects  

You can't use reverse and limit use .sort  

When dealing with nested array/matrix questions think about work in the outer row loop in terms of adding things  

Can't iterate over an object with a regular for loop so either use the for loop that iterates through objects or store object in an array so you can loop with the regular for loop or while loop  

Closure methods naming convention the outer function should include something like a gate in the name and the inner function should be something with the name of the door  

Also depending on the problem, you may have to loop so talk about using a loop or recursion comparing the two and talking big O  

When comparing values focus on two points this applies to array problems and trees where the traversing from point a to point b or comparing values  

Identify any repetition, bottlenecks, or unnecessary work.  

The bottleneck has the biggest impact on runtime complexity so focus on that more but runtime can also be affected by Unnecessary & Duplicated work.  

## End  
After coding a naive approach. (your first naive approach might be Greedy/Optimal sometimes if your very good still do a naive to explain your process) and go step by step 

Talk about the overall runtime and space complexity of your code.  

Explain trade-offs and how the code/approach can be improved if given more time.  

Ask questions. More importantly, ask good and engaging questions that are tailored to the company! Pick some questions from your list.  

## Other  
If an interview will give you a harder question after you answer a question that's good they trying to see how high level are you  

If you go to another interview and they give you something unexpected to talk about tell them you didn't expect it and ask for another time to try so you can recenter if the interview is behavioral  

## Hacker rank (supports vim)  

you can look at the documentation for the hacker rank challenge  
ask the recruiter if you can lookup official documentation  

You can use a second computer since hacker rank checks window focus if you wanna look at other stuff  

Be aware of the time on hacker rank also sometimes they disable intelligence disable the ability to go back to a question  

Maybe hide timer  

Startups might read comments  


## Take-Home Project and Code Review  
You are given an assignment to complete ahead of the onsite interview  
You should be provided clear instructions and minimum specs  
You may be provided a starter code  
You are given between 2-7 days to complete (manage expectation)  
If your submission is approved, you will be called in for a code review with an engineer  
Prepare to give the engineer a walk-through of your app and discuss:  
Design decisions  
Tradeoffs you made and why  
Bugs that you or the interviewer found  
Plan for continuing  
Considerations for improving security, performance, usability, etc...  
You may be asked to code a new feature or project during the interview