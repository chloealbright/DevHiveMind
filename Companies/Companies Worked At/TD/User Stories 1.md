>[!important] Scrum master is there to address blockers and help move things like reaching out to stakeholders on your behave if they aren't helping you out  with what you need. 

The flow from themes to epics to features to user stories can vary depending on the specific project management or development framework being used. However, there are commonly accepted practices in many agile methodologies.

In the Scrum framework, for example, the typical flow is from:

1. **Themes:** High-level business objectives or goals.
2. **Epics:** These are large, high-level entities that represent big, overarching initiatives or goals. Epics are usually too broad to be completed in a single iteration or sprint.
3. **Features:** Epics are decomposed into features, which are more manageable and focused units of work. Features are still relatively high-level and may take several sprints to complete.
4. **User Stories:** Features, in turn, are broken down into user stories. User stories are more granular, detailed, and focused on a specific functionality or requirement and written from the user's perspective. They are the smallest units of work that can be completed within a single sprint.





close issue clone if it is crossing into new sprint also comment
  
Knowledge management is confluence

There's PR planning for platforms not practices but to TD has adopted and done it for the practice or practice construct  

If you have multiple stakeholders in a story they may have different or misaligned acceptance criteria

Clone and close when work is done for stories otherwise if no work done move over


  
User stories can have multiple personas so you can have multiple  
  
  
As persona A  
  
As persona b  
  
As persona c  
  
  
I want to...

# Pi Planing 
***Need about 46 story points of work for each PI***
**Only do 6 story points of work near PI planning**
*Move backlog to Epic for Next PI*
TD Bank follows a non-standard fiscal year shown below

## Pi planning Q1
### October November December   

takes time out of sprint 1 of the first quarter in December to prepare for next PI


## Pi planning Q2  
### January February March  

takes time out of sprint 1 of the second quarter in March to prepare for next PI


## Pi planning Q3
### April May June  

takes time out of sprint 1 of the third quarter in June to prepare for next PI


## Pi planning Q4 
### July August September  

takes time out of sprint 1 of the fourth quarter in September to prepare for next years first PI

>[!note] 
 Regular fiscal year Q1 starts in January and follows 3 month increment until end of year or Q4 which starts October



# Business Requirements 
business requirements refer to the high-level needs/wants and objectives of the organization or stakeholders that drive the development of a product or service.

also acts as a driver for user stories

# Features  

Features are high-level changes that the organization wants for their customers that should be less than a year  

They break down to 3 month Epics and which break down to small user stories to fit in 2 week sprints of work for pods to work on they describe functionality defined by the product group  

Feature goes to epic which goes to story which goes to uml which goes to code


> Epics follow a theme so you need better understanding of the themes ie bank and finance system 
Completed Epics which is a list of completed stories get converted into features that aligned with themes  
Definition of success 
Is there anyone doing what your trying to do  
Aligning definitions 
Possibly redefining definitions  

# Epics in Depth

OKR are converted into epics and have a theme

Epic has acceptance criteria

Features are detailed and programmable

Epics can be 1 sprint at minimum or 2 weeks or can span across all 6 sprint within a Quarter 

so 1 quarter has 6 sprints or 12 weeks then PI plaining for next Quater with 6 sprints

you can combine epics, have it roll over into another sprint 

stories need to be closed in order to close epics 

and epics might be created at the product group level

Martha Shipra and Wendy have epics in general anybody can have one but they Just specifically have one

>[!note] There will be a continuous improvement epic that you may be creating a story for improving something that exists 

# Shirt/sprint size 

XS less then 1 sprint or 2 weeks should considered weather this is a story then an epic 

S 1 to 2 sprints about a month  

M 2 to 4 sprints or 1 to 2 months 

L 4 to 5 sprints or 2 to 3 months  

XXL or XL greater then 5 to 6 sprints and should be considered to be broken into 2 epics 

# Split a Story 

Story has multiple items (words such as "and" or "or" appear  

- All of these conditions necessary right now? 

Too many workflow steps for user  

- Are all these steps necessary right now? 

Happy path Vs alternative paths  

- Are all the alternative flows necessary right now? 

Operations based story 

- Are all the operations necessary right now? 

Acceptance Criteria  

- Different stories to handle different scenarios  -All test scenarios necessary right now? 

Variations in Data/Interfaces/Platforms  

- Are all these options necessary right now? 

Use cases are scenarios where you represent multiple parties that have to be involved or maybe involved  

	You have two types of relationship extend where maybe additional behaviors added   And include which is The baseline relationship  
	
	Stories focus on the who, what, and why while use cases are more detailed include process flows for users with in depth guidance  

[https://www.techtarget.com/searchsoftwarequality/answer/What-is-the-difference-between-a-user-story-and-use-case-in-software-testing](https://www.techtarget.com/searchsoftwarequality/answer/What-is-the-difference-between-a-user-story-and-use-case-in-software-testing) 

Purpose of stories create a persona in an arbitrary situation where that persona is hitting multiple touch points within the story with a product of some sort example   

As persona Joe I need / want this feature so I can.. business benefit and effect   

As a user, I want to be able to set reminders to take my medications or supplements so that I don't forget to take them. 

Story consist of Acceptance criteria which is a checklist of key things to provide a better understanding of boundaries and behavior of the story And test scenarios where you can validate the story has been delivered correctly  


## Attributes of Requirements/User-story
**Stories and requirements are a little similar in terms of attributes but different 
also requirement which are specification on implementation are defined at user story level **

Requirements/userstory definition should be a high level description not to detailed in general because it can change

User stories needs to be from customers standpoint

*can also come up in discovery*

- Cohesive - Relates to a single topic, such as a business process, interface, event. All related requirements should relate to and support the same purpose

- Complete - All needed aspects are documented, and the requirement is self-contained

- Consistent - Doesn't contradict other requirements and is uniquely specified. Level of detail is similar to other like requirements

- Correct - Reflects business needs as specified by the use/subject matter expert

- Modifiable - Can be changed. Requirements must be organized and logical to be modifiable

- Unambiguous - specific so everyone can understand 

- Feasible - realistic 

- Testable - Specified in such a way that a requirement can be tested to see that is was correctly implemented

# Acceptance criteria 

You can develop a criteria at the beginning when creating a story In the middle and at the end when it's more flushed out you may think of something that is important that encompasses the whole story 

Acceptance criteria is written from the product perspective It defines scope and is one of the definitions of done

Acceptance criteria is like a list of things that happen depending on the process flow and what occurs so let's say for example we have this user story:

> As a website visitor I can see all flights departing from my selected airport to my desired destination on the selected day to pick flight that meets my travel needs 

You may run into things in your acceptance criteria that may end up with you creating more user stories for the future

**There can be multiple acceptance criteria which can be converted into a story with its own acceptance criteria

The definition of ready is typically used at the user story level rather than at the acceptance criteria level.

user story can present as an acceptance criteria

# The criteria would be (Breaks down to CRUD)

The visitor can see a list of all available flights that fit the criteria  

If no flight fit the criteria the visitor can choose to see alternative dates 

If no flights fit the criteria the visitor can choose to see alternate destin  

If no flight fits the criteria the visitor can choose to see alternate departures  

Once the visitor picks a flight the booking window will be offered  

This would be criteria in scope in relation to the story and an example of an out of scope criteria would be maybe visitor can get points or something  


Another example is  
	Fred request recommended training topics 

		Given Fred is logged into website 
		And Fred has unfinished training topics 
		When Fred request training plan 
		Then Fred customized training plan is viewable  

Don't work on stories that don't meet the definition of ready  

Single user story should have multiple acceptance criteria 

# Definition of ready 

Basically means we must understand and agree what the story is as a team so from the developers to the BSA etc...  

Story in limbo stays in backlogs

Everybody's hearing what the other parties need and will do Which improves code 

	Clear business value 
	
	Manage defects  
	
	Defined user story with clear Narrative/Overview 
	
	Make sure epics aligning with feature/theme 
	
	Identified dependencies, risk, & constraints 
	
	Identified Priority
	
	User Persona if needed in the context of story

	Time estimation you should personally avoid not always obvious but give general  

	
	Access the effort and time needed in addition to the complexity  
	
> Have Clear Acceptance criteria(Specifications & Conditions) & data sets that are in place 
> Acceptance criteria pull from [[User Stories#Attributes of Requirements/User-story | Requirements/User Stories ]]

	
	Should be testable with the ability to test target functionality 
	
	Boundary scope guideline alignment to future Unknowns  

	Have a definition of done to aim for to know that work is completed

  #  Whose job is it to get the story ready BSA and Journeys how do these parties work with business aligned platform 

Product Owners are the ones who refine the product backlog and determine what stories/requirements get prioritized and populates the sprint backlog within pods based on things like:  

Historical capacity               

Technical dependencies External team dependencies    


# Things to think about  

Which items did you reprioritize (and why)?  
Which stories can you estimate? Do you have enough information?  
Which ones meet the Definition of Ready?   
What considerations/dependencies remain? 

# Definition of done 

As a team create a checklist of 7 activities or less for every given user story of a particular type.   Things that can be on the checklist is it must pass unit and integration test or security must be implemented to abide by some type of regulation 

Completion of code review  

Acceptance Criteria met 

All dependencies are accounted and completed including task and sub task related to stories 

Test cases are executed and passing 

No open defects 

Then when done deployment happens to target environment  
   
# Old way of Estimation   

Create a incomplete requirement specification  

Create and incomplete design specification  

The reason you create and complete specifications is because that's how they usually start it's rare that you get a complete specification on the first try   

Then you make your estimation based on past projects that are similar or historical practices  

Submit estimate with a caveat adding about 25% more time to your expected estimate so if you think it's going to be an hour make it like 3 hours or in the long-term a week 5 weeks etc....  

Padded estimates usually get cut and the caveats mention are ignored  

You get a new timeline   

So be aware what you are picking when working   

New way estimation or relative estimation   


Vote between people to get a better more accurate estimate by assessing how long it will take to complete something during this process you may see that you may have different ideas about how long it should take and while having this conversation you may discover why they think it might take less time and get a clear understanding on what needs to be done or you might discover something else that makes it longer and come to a better understanding and estimation and pad accordingly