---
tags:
  - web
  - frontend
  - library
  - react
  - redux
  - javascript
  - typescript
author:
  - jacgit18
Comments: This documentation discusses
Status: Done
Started: 
EditDate: 2024-02-07
Relates:
---
```javascript
const DO_ACTION = 'DO_ACTION';

function doSomething() {
  return {
    type: DO_ACTION,
    info: 'First Redux action'
  };
}
// Actions can also involve asynchronous operations, such as making API calls.
```