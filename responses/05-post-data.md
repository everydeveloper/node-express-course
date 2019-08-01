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
Notice how we used app.post this time instead of app.get. We also compared the values passed from the request body to see if they match our mock data (which would normally come from a database). If they match, it will send a JSON file with an additional value, where a token could be stored. However, if they don't match, it will return an error message (without the token).

**Pro-Tip:** As a security precaution, you should never save passwords directly into your database. Use a tool like [bcrypt](https://www.npmjs.com/package/bcrypt) to save a hashed version, which will be decoded at login.

When you are finished with this section, close this issue and [click here]({{ repoUrl }}/issues/6)