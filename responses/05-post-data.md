So far, we have only made GET requests to our server. A POST request can send data securely through the request body. In order to make POST requests, first we need to include the "body-parser" library from our node_modules (included with express). Add these lines after the app variable:
```javascript
const bodyParser = require('body-parser');
app.use(bodyParser.json());
```
 
Let's write a function to handle a POST request made to the 'login' endpoint, as if a user was trying to log in:
```javascript
app.post('/login',function(req,res){
 	const username=req.body.username;
 	const password=req.body.password;
 
 	const mockUsername="billyTheKid";
 	const mockPassword="superSecret";
 
 	if (username===mockUsername && password===mockPassword){
      	res.json({
      	 	success: true,
      	 	message: 'password and username match!',
      	 	token: 'encrypted token goes here'
      	})
 	} else {
      	res.json({
      	 	success: false,
      	 	message: 'password and username do not match'
      	})
 	}
})
``` 
Time to commit our changes!
```
git add server.js
git commit -m"add login POST route"
git push origin master
```
