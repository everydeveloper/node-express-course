In Express, words with a colon in front of them in the url are treated as variables. You can access the value of each variable through req.params, like this:
```javascript 
app.get('/users/:id',function(req,res){
	console.log(req.params.id)
	res.json({
		success: true,
		message: 'got one user',
		user: req.params.id
	})
})
```

_Let's test it out!_

Add the function above your `app.listen` function in your server.js file, restart the server, and paste this into your browser url: http://localhost:8000/users/mark

Now check the terminal for the console.log of req.params.id. You should see the name 'mark', since it is the value we passed in place of the 'id' variable. Since we are running this in the terminal, our console.log will appear there (instead of the browser).

After testing that it works, push your changes your GitHub repo:
```
git add server.js
git commit -m"add dynamic GET route"
git push origin master
```

