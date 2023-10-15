

  

typically when it comes to state when network request are being handle of data from a db it might be structured like

  

```javascript
state = {

loading: true,

data:[],

error:''

}
```

  

  

data by a list of some thing like a news feed of post from user

  

error to display error

  

reducer would have different cases

  

where new loading, data, & error are returned