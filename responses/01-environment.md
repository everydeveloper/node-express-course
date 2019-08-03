## Installation   

First, let's [install Node.js](https://nodejs.org/en/download/), and an app called [PostMan](https://www.getpostman.com/downloads/) to test our API. You will be coding along with me, so make sure you also have [git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

Node.js comes with something called NPM (Node Package Manager), that we will use manage our node modules. You can check if you have Node, NPM, and Git installed by running these commands:
```
node -v
npm -v
git --version
```
You should get a version back from each of these commands, if it was correctly installed.

## Clone Template Repository
By signing up for this course, a [template repository]({{ repoUrl }}) was created on your github account. Clone this repository locally on your computer and navigate to it by running:
```
git clone {{ repoUrl }}.git
cd node-express-server-intro
```
## File Setup
Open the folder you just cloned in your favorite text editor.
You should have a few files already created:
```
-middleware.js
-.gitignore
-server.js
```
The server file will be the main one we use, and middleware will be used near the end. In the .gitignore folder, you should see this line at the top `/node_modules`

Express (the server library we will install) is a node_module. Rather than track the entire library in our git history, we will create a package.json file, which will allow us to install and save node modules: `npm init -y`

You should have a package.json file in your folder now. 

Now you can install Express using NPM. Enter this command in the terminal:`npm install express --save`

A folder called node_modules should apear in your project. This is where the actual files for express are stored. If you open the folder, you can see how many files there are (which is why we added this folder to our gitigore file). 

In your package.json file and make sure you have something like this under your dependencies:
```json
"dependencies": {
    "express": "^4.17.1",
  }
```
The number on the right is the version you downloaded. Since we aren't tracking the actual `node_modules` folder, this section is a reference used to re-install the modules your application depends on.

When you are finished with this section, push your file to github for the next step:
```
git add .
git commit -m"initial file setup"
git push origin master
```