Notice how we used app.post this time instead of app.get. We also compared the values passed from the request body to see if they match our mock data (which would normally come from a database). If they match, it will send a JSON file with an additional value, where a token could be stored. However, if they don't match, it will return an error message (without the token).

💡 As a security precaution, you should never save passwords directly into your database. Use a tool like [bcrypt](https://www.npmjs.com/package/bcrypt) to save a hashed version, which will be decoded at login.

With this last push, your [repository]({{ repoUrl }}) should look [like this]({{ repoUrl }}/tree/05).

[Click here]({{ repoUrl }}/issues/7) to learn how to test a POST route. 