We can make GET requests all day through the browser url, but to make a POST request, we need to get more sophisticated! Open up the PostMan App, and look for an input field that says: "Enter Request Url". It is between a dropdown menu and a Send button.

<img src='{{repoUrl}}/raw/master/postman.PNG' alt="screenshot of postman">
 
First, change the dropdown on the upper left from GET to POST. Next, enter our login url next to the dropdown (http://localhost:8000/login). Before you hit send, we need to change a few things.
 
Click the "Headers" tab, and enter the key: Content-Type. In the box just to the right, enter the value: application/json. This tells the server the request is going to be in JSON format.
 
Next, click on the "Body" tab. In the dropdown below, change the value to "raw", and enter the login data below:
```json 
{
"username":"billyTheKid",
"password":"superSecret"
}
```
Restart your server, to make sure you have the latest version running (with body-parser and our post function). Click send in PostMan, and you should get a positive response from the server. 

When you get a response, close this issue for the next step.
