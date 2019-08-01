Switch back to the top of our server.js file and import the middleware file we just created like this:
```javascript
const middleware= require('./middleware.js')
```
Now we can include our middleware function in a protected route endpoint.
```javascript
app.get('/admin', middleware.checkToken, function(req,res){
res.json({
Success: true,
      	Message: 'admin authorized',
      	adminData: 'secure data from the database'
      	})
 	})
```
Notice how we include our middleware function in between the route and our protected function? By calling next in each of these comma separated functions, it runs the next function on the list.

Try adding an authorization header in postman, then make a get request to the admin endpoint.

**Pro Tip:** Use something like [JSON Web Token](https://www.npmjs.com/package/jsonwebtoken) in place of our mock token, since it is encrypted and secure. 

When you are finished with this section, close this issue and [click here]({{ repoUrl }}/issues/9)