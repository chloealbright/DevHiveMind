
  
home is login screen where user can save login info and they can log in with there fingerprint or the same thing but when user save info and sign the home page changes to the map  
  
can include error dialog menu which isn't changing pages so draw a square with a half-circle on top  
  
  
you can include multiple transitions and triggers ie buttons  
Add alert feed button to home tab on the map  
be less conversational in presentation  
  
Glossary must be specific to your application  
Avoid general definitions  
And break down rules to one sentences  
for business rules presentation  
  
Think about computer problems like logging in and clicking on links to pages and picking option in pull-down list and checking class status and alerting user when status changes or number of seats reduce  
  
  

  
Use case diagram  
--------------------------------  
the arrowhead indicates who is initiating the use case so if you have multiple actors connected to one use case then one you may have one actor who is just taking part of the case without an arrowhead  
  
time is an actor in a scheduled use case like subscription payments  
  
Possible VPN test use case  
---------------------------------------------------  
You do not exactly detect that someone is using a VPN. What you do, if you are a company like Netflix, is to keep a list of all known VPN exit IP addresses. So if someone tries to log in to Netflix and their IP is on the list, then they can't log in.  
I am sure you could plant a virus on a person's PC and detect whether they are using a VPN that way also.  
  
/////////////////////////////////////////////////////////////  
for use case scenario write out in a sequence of steps. for initial senario than for alternative senario base it on steps mentioned on first senario like something going wrong or changing at one of the steps like user loggingin and putting invalid login but focus on a more complex step of that initial senario  
  
user may leave parking spot because to small or illegal parking spot like a hydrant or bus stop  
  
alert pops up user sets destination  
  
Avoid parking in the shade  
include time as an actor for use case diagram for subscription services  
  
system cant be in use case because they aren't external like a user or credit card company  
  
  
  
  
3606 robust tips  
-------------------------------------  
change middle to control and first part to page to keep description one line and or try to get text inside circle instead  
also for external actors like payment create a boundary to interface with  
  
can use a scheduler process which is used by time actor  
  
robust case notes  
----------------------------------  
Robust diagram is structural not flowing  
  
the entity is data or temp data/memory  
put arrow heads to avoid bidirectional  
  
user launches app through phone (boundary interface) user access controls like tab temp creating(Entity domain) or user a different Entity  
or  
user boundary registration screen control registration process ..  
  
also use different actors  
so actor -> boundary interface ->  
  
  
log entity  
  
boundary and entity are dumb  
  
LDM  
------------------  
information about outside actor like bank can be used  
Draw a Logical Data Model Diagram, including all classes, attributes, associations (bi- or uni-directional), association labels, and multiplicities.  
  
avoid to many " many to many" relationships in database 0..*  
  
  
change name convention and think databases  
  
Component Diagram  
------------------------------------  
Components contain classes and can be used to hide classes  
  
antenna only sends out messages not receive  
  
2 bars for synced processes not one in activity diagram  
  
Sequence diagram  
------------------------------  
 is for one process path no alternate path or decision or condition  
  
  
Package diagram tip  
------------------------------------  
  
the diagram without classes is used to hide the package contents  
  
also starting package should have the least dependencies meaning arrows should not come from the package however it is ok to have other packages be dependent on that package but it cant be dependent to other packages if it is the starting point  
  
and anything in between or at the end can have or should a couple  
  
not all packages need to be connected to each other the arrows represent dependencies meaning it needs the other classes or packages to run as oppose to just running the class  
  
[https://creately.com/blog/diagrams/uml-diagram-types-examples/](https://creately.com/blog/diagrams/uml-diagram-types-examples/)