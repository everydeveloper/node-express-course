In order to start using the middleware function, we need to import it in our server.js file. Add this near the top of server.js:
```javascript
const middleware= require('./middleware.js')
```
Now we can include our middleware function in a protected route endpoint.
```javascript
app.get('/admin', middleware.checkToken, function(req,res){
res.json({
	success: true,
	message: 'admin authorized',
	adminData: 'secure data from the database'
	})
})
```
Notice how we include our middleware function in between the route and our protected function? By calling next in each of these comma separated functions, it runs the next function on the list.

When you finished this step, commit and push to github:
```
git add server.js
git commit -m"add middleware to admin route"
git push origin master
```