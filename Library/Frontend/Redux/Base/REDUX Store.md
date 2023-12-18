---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
```javascript
reateStore = redux.createStore

applymiddleware = redux.applymiddleware

loggerMiddleware = reduxLogger.createLogger()

thunkMiddleware = redux-thunk.default

  

store = createStore(reducer)// for one reducer

store = createStore(rootReducers, applymiddleware(logger, thunkMiddleware))

//initial state can be gotten with

store.getState()

  

// registers listeners

store.subscribe(listeners)

unsubscribe = store.subscribe(() => log updating state store.getState())

  

// then dispatch which takes action as param and cause state transition

  

store.dispatch(doSomeThing())

store.dispatch(doSomeThing())

store.dispatch(doSomeThing())

// alt dispatch is Bind Action Creators not really used

const actions = bindActionCreators({doSomeThing, otherAction},store.dispatch)

actions.doSomeThing()

unsubscribe() // rest or state changes
```