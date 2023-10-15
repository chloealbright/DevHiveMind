
takes in slice which are acting as reducer


```javascript
const configureStore = require('@reduxjs/toolkit').configureStore

const cakeReducer = require('../features/cake/cakeSlice')

const icecreamReducer = require('../features/icecream/icecreamSlice')

const userReducer = require('../features/user/userSlice')

  

const store = configureStore({

reducer: {

cake: cakeReducer,

icecream: icecreamReducer,

user: userReducer

}

// have to appendto default middleware in toolkit

middleware: getDefaultMiddleware => getDefaultMiddleware().concat(logger)

})

  

module.exports = store
```