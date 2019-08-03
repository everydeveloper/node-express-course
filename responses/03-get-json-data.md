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
Let's save your changes on github:
```
git add server.js
git commit -m"add first GET route"
git push origin master
```