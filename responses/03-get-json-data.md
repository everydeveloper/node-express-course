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
You just made your first endpoint! This function will respond to a GET request at http://localhost:8000/users with a JSON file, which includes our mockData under the key 'users'. Let's test it out!

Make sure you restart your server (since we changed the file) then open a browser and navigate to http://localhost:8000/users
You should see a JSON file, returned from the server!
