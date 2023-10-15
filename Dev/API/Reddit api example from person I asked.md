Okay. So a few things up top, in your /test route, you're not quite setting the headers correctly. The req variable refers to the incoming request (i.e., that your own client is making), not the outgoing HTTP request you're going to make to reddit, so you don't want to set the headers there, you want to set the headers in a configuration object that you send with fetch (or axios).  
  
I'm including a reference to a function that I use to get the access token, it should be helpful to you (the authorization code function is react-native specific). Notably you'll need to use FormData rather than JSON to send the information.  
  
```javascript

const tokenUrl = '[https://www.reddit.com/api/v1/access_token'](https://www.reddit.com/api/v1/access_token');  
  
  
const token = app.post(tokenUrl, (req, res) => {  
const tokens = req.setHeader(process.env.CLIENT_ID, process.env.SECRET_ID);  
const userData = {  
'grant_type': 'password',  
'username':process.env.USERNAME,  
'password': process.env.PASSWORD  
}  
  
// const userId = jwt.decode(token);  
// const user = users[userId];  
  
// res.send();  
  
// res = req.post(tokengetter, token, userData, headers);  
// res.json()  
  
})  
  
app.get('/test', async (req, res) => {  
await req.setHeader('content-type', 'application/x-www-form-urlencoded');  
await req.setHeader('Authorization', `Bearer ${token}`); // after you have token  
const request = await fetch(urlReddit, req.headers);  
// const request = await axios.get(urlReddit, requestOptions)  
  
const data = await request.json();  
// const data = await request;  
  
  
// body stuff if needed  
  
res.send(data);  
});

```