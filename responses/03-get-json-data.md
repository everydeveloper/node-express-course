Now that our server is listening for requests being made on localhost:8000 let's return some mock JSON data. Add the following to your server.js file:
```javascript
const mockUserData=[
{name:'Mark'},
{name:'Jill'}
]
app.get('/users', function(req,res){
 	res.json({
 	 	success: true,
 	 	message: 'successfully got users. Nice!',
 	 	users: mockUserData
 	})
})
```
Overall your file should look like this:
```javascript
const express = require('express');
const app = express();

const mockUserData=[
	{name:'Mark'},
	{name:'Jill'}
]

app.get('/users',function(req,res){
	res.json({
		success: true,
		message: 'successfully got users. Nice!',
		users: mockUserData
	})
})

app.listen(8000,function(){console.log('server is listening')})
```
Let's save your changes on GitHub:
```
git add server.js
git commit -m"add first GET route"
git push origin master
```