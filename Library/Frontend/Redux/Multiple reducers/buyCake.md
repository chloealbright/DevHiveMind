---
tags: 
author:
  - jacgit18
Comments: This documentation discusses
Status: 
Started: 
EditDate: 
Relates:
---
```javascript
export const BUY_CAKE = 'BUY_CAKE'

  

import { BUY_CAKE } from './cakeTypes'

  

export const buyCake = (number = 1) => {
	return {
		type: BUY_CAKE,
		payload: number
		}

	}
```