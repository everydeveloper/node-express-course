In Express, words with a colon in front of them in the url are treated as variables. You can access the value of each variable through req.params, like this:
```javascript 
app.get('/users/:id',function(req,res){
console.log(req.params.id)
})
```
After adding this code to your script.js file, and restarting the server, paste this into your browser url: http://localhost:8000/users/mark
Now check the terminal for the console.log of req.params.id. You should see the name 'mark', since it is the value we passed in place of the 'id' variable. Notice that we didn't actually return anything from the server this time, so the browser should appear unresponsive.
