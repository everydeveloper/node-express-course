One of the benefits of a server is security. You don't want to send data from the database directly to the browser. A server can give you control over who is authorized to retrieve protected data.

We added some basic authentication (proving that you are who you say you are) by checking the user's password. However, we haven't used this information to authorize them to do anything. Usually this happens by sending and encrypted token at login, which is stored in memory and added to the headers when making a request.

In Express, you can use middleware functions to protect certain routes. Start by opening the middleware.js file and write a function called "checkToken" that accepts three arguments (req, res, and next):
```javascript
const checkToken=function(req,res,next){}
```
This function is going to test if the user supplied a token in the request headers. If they did, it will call next(), which will trigger the protected function. If it does not pass, the function will send an error message as a response, and will not continue to the protected function. Our checkToken function should look like this now:
```javascript
const checkToken=function(req,res,next){
 	let token=req.headers['authorization']
 	if(token){
 	 	next()
 	} else {
 	 	res.json({
  		success:false,
  		message:'no token supplied'
  	})
 	}
}
```
Since we included this function in a different file, we should export it to use in our main server.js file. Add this line to the bottom of middleware.js
```javascript
module.exports={checkToken:checkToken}
```
Let's push these changes to github:
```
git add middleware.js
git commit -m"add checkToken function"
git push origin master
```