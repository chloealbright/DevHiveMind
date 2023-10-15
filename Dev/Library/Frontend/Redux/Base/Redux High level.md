![[unnamed.gif]]

A state management library  
  
That follows 3 principles which is  
  
Has one source of Truth which is a store of State that is read only and changes statement using pure functions you call almost imagine it like a tree structure in a sense  
  
Store is the source of Truth that is an object that describes the whole state of the application or a website  
  
  
Being read only makes it immutable which helps prevent unexpected errors so essentially we're quitting a new state after each action  
  
Changes are only made with pure functions meaning a function that takes in an input and gives an output that is predictable  
  
UserAction > reducer > store > StateChanges  
  
There are many actions so the reducer helps by taking in the user input with a reducer which is a pure function and the reducer spits out a output which is a new state that updates state also known as the store which is the entire state of the app.  
  
redux follows a flux pattern  
action > dispatcher > store > view  
with this pattern data flows on way this better then mvc pattern  
  
As apps scale up the number of reducers goes up and the actions go up so you want to create a root reducer in the store to handle all these reducers  
  
You can pass the store to the app as a prop  
  
but you don't want to pass your store to the app and all the lower components over and over again that will affect the performance  
  
Also in between action and reducer there is a tunnel that the action passes which is known as middleware where you can modify the action  
  
That's why you needed provider component from react-redux  
  
action > controller > model(multiple) > view(multiple)  
  
  
learn redux boiler plate code which basically repetitive work  
  
then transition to redux toolkit  
  
notes  
-------  
provider store lets you access state > because we pass the store to provider which wraps the app  
  
provider connect redux to react so you can manage state  
  
provider makes it so you dont pass the store to the app all time since that will affect performance  
  
coonect is a higher order function that makes component a smart component meaning it is aware of redux state store  
  
  
  
Libraries  
-----------  
[https://www.gatsbyjs.com](https://www.gatsbyjs.com/)  
[https://github.com/reduxjs/reselect](https://github.com/reduxjs/reselect)  
[https://redux-saga.js.org/](https://redux-saga.js.org/)  
[https://immutable-js.com/](https://immutable-js.com/)  
  
docs  
------  
[https://redux.js.org/introduction/getting-started](https://redux.js.org/introduction/getting-started)  
[https://redux-toolkit.js.org/introduction/getting-started](https://redux-toolkit.js.org/introduction/getting-started)  
[https://github.com/LogRocket/redux-logger](https://github.com/LogRocket/redux-logger)


