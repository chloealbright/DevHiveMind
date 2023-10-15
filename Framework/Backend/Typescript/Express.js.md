Express is a back-end  [[Node.js]]

-   Routing to determine how an application responds to a client request coming in at a particular endpoint, which is considered a URI (or path) and a specific HTTP request method (GET, POST, and so on).

To have more control over the exact string that can be matched by a route parameter, you can append a regular expression in parentheses (()): 

Route path: /user/:userId(\d+) 

Request URL: http://localhost:3000/user/42 

req.params: {"userId": "42"} 

Because the regular expression is usually part of a literal string, be sure to escape any \ characters with an additional backslash, for example \\d+.




Route handlers 

You can provide multiple callback functions that behave like [middleware](http://expressjs.com/en/guide/using-middleware.html) to handle a request. The only exception is that these callbacks might invoke next('route') to bypass the remaining route callbacks. You can use this mechanism to impose pre-conditions on a route, then pass control to subsequent routes if there’s no reason to proceed with the current route. 

Route handlers can be in the form of a function, an array of functions, or combinations of both, as shown in the following examples. 

```javascript
// A single callback function can handle a route. For example: 

app.get('/example/a', (req, res) => {   res.send('Hello from A!') })  

// More than one callback function can handle a route (make sure you specify the next object). For example: 

app.get('/example/b', (req, res, next) => {   
console.log('the response will be sent by the next function ...')   
next() }, 
		(req, res) => {  
		 res.send('Hello from B!') 
		})  

// An array of callback functions can handle a route. For example: 

const cb0 = function (req, res, next) {   console.log('CB0')   next() }  

const cb1 = function (req, res, next) {   console.log('CB1')   next() }  
const cb2 = function (req, res) {   res.send('Hello from C!') }  

app.get('/example/c', [cb0, cb1, cb2])  

// A combination of independent functions and arrays of functions can handle a route. For example: 

const cb0 = function (req, res, next) {   console.log('CB0')   next() }  const cb1 = function (req, res, next) {   console.log('CB1')   next() }  app.get('/example/d', [cb0, cb1], (req, res, next) => {   console.log('the response will be sent by the next function ...')   next() }, (req, res) => {   res.send('Hello from D!') })

```