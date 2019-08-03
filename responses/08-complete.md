Alright, now your admin route is secure! 👮

Try adding an authorization header (with any value) in postman, then make a get request to the admin endpoint. You should get a success response. Try again without the authorization header. You should get the 'no token supplied' response from our middleware function. 

If not, see if your [repository]({{ repoUrl }}) looks [like this]({{ repoUrl }}/tree/08).

💡 Use something like [JSON Web Token](https://www.npmjs.com/package/jsonwebtoken) in place of our mock token, since it is encrypted and secure. 

[Click here]({{ repoUrl }}/issues/10) to finish this course!