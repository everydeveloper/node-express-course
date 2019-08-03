Alright, now let's start making a server! Open up your server.js file and add these two lines:
```javascript
const express = require('express');
const app = express();
```
The first line gives you access to the express library by searching your node_modules for "express". The next creates an instance of the express constructor, which we will name "app".
We can now access methods used for making a server by including their name after app. Add this to the bottom of server.js:
```javascript 
app.listen(8000,function(){
console.log("server is running")
})
```
The app.listen method will start up the server locally on the port you give as its first argument (in this case the base url is: http://localhost:8000)
 
But first we need to run the server.js file by entering this in the terminal: `node server.js`
 
If everything was successful, you should see the console.log message we supplied in the callback: "server is running". This happens because the file is being run on our terminal. To end this process, push **CTRL**+**C**. Whenever you make changes to your server, you need exit and restart it.

If your server is running, push your changes up to github to complete this step. 
```
git add server.js
git commit -m"set up express server"
git push origin master
```