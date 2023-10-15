
Just use es5 imports  & exports for now unless you're using react where you can use es6 without any problems look at modules notes for more info

might not be the case specifically when you use node


If you are importing the default, there has to be a default. 

In general, the community appears wary of default exports at the moment as they seem to be less discoverable (I have no specific citation, but I've watched the conversation!) 

If you are working in a team, whatever they say is the correct answer, of course! 

So without a default, you need to use: 

```
import * as service from "../service"; 
```
Or choose a specific thing: 

```
import { specificNamedThing } from "../service"; 
```

A module (as an example, a Javascript file like my-module.js) can export functionality or objects from itself for use in other modules. This is fundamental in adhering to a bunch of coding principles, like code-reuse and separation of concerns. In modules, we find exports in two ways: 

	by using export on different functions or objects. 

	by using export default on a single function or object. 

When a module needs to import functionality from another module, it has a number of options available: 

	Import all exports into current module scope — import * from "my-module.js" 

	Import particular named exports — import { func1, obj2 } from "my-module.js" 

	Import the default export — import func from "my-module.js" 

Run a module’s global code but not import anything — import "my-module.js" 

Dynamic importing a module — import("my-module.js").then((module) => { //...do something }) 

For most use cases, especially if you’re a React developer, importing named and default exports will be what you’ll primarily use. 

There are use cases where you’ll import into the current module scopes (like project constants defined in a JS object) or dynamic import (for code-splitting) but more often than not it’s just the default and named exports that you’ll focus on. 

Import aliases are where you take your standard import, but instead of using a pre-defined name by the exporting module, you use a name that is defined in the importing module. 

## Why is this important? 

There may a be time where you find yourself requiring imports from multiple different modules but contain exports named the same. Javascript doesn’t like this. 

```
Failed to compile. 

/Users/gregbyrne/Project/One/src/pages/index.js 

SyntaxError: /Users/gregbyrne/Project/One/src/pages/index.js: Identifier 'Card' has already been declared (6:9) 

  4 | import { Button } from '../components/button' 

  5 | import { Card } from '../components/card' 

> 6 | import { Card } from 'react-native-elements' 
```

A common example where you may come across this problem is providing a project-level abstraction over a dependency. 

For example, using a component library directly in your screens can make your project highly-coupled with the implementation of that component library. In the future, your project may switch that dependency and if it wasn’t abstracted, you may find it isn’t as simple as switching imports. That’s where project abstractions come to the rescue. 

```
// Card.js in project/src/components/card 

import { Card } from "cool-component-library" 

const Card = () => ( 

    // abstraction over cool-component-library card  

    // suitable for your project needs 

) 

const ListCard = () => ( 

    // like above 

) 

export { Card, ListCard } 

// --- 

// Index.js in project/src/pages 

import { Card } from '.../components/card' 

// ... index page code 
```

The eagle eyed reading this would see from the above that Card.js won't compile because of the declaration error as before. 

## Differentiating your imports 

So we come full circle to Import aliases. These will allow you to import similarly named exports for use within your module. 

### TL;DR 

When importing from a named export, e.g. 

```
// my-module.js 

// ... code .. 

export { Something1, Something2} 
```

You can alias the import using as: 

```
import { Something1 as MySomething } from "my-module.js" 
```

For importing default exports, e.g. 

```
// my-module.js 

// ... code .. 

export default Something 
```

You can alias the import directly: 

```
import MySomething from "my-module.js" 
```

With the example above on the Card component project abstraction, we can solve the compile error by aliasing the named export. 

```
// Card.js in project/src/components/card 

import { Card as CoolCard } from "cool-component-library" 

const Card = () => ( 

    // abstraction over cool-component-library card  

    // suitable for your project needs 

) 

const ListCard = () => ( 

    // like above 

) 

export { Card, ListCard } 
```

If it happens to be a default export, we can still alias it. 

```
// Button.js in project/src/components/button 

import CoolButton from "cool-component-library-button" 

const MyButton = () => ( 

    // code 

) 

export default MyButton 

// --- 

// Index.js in project/src/pages 

import Button from '.../components/button/Button.js' 

// ... index page code
```