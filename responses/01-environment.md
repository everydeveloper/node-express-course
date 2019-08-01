First, let's [install Node.js](https://nodejs.org/en/download/)
We will be using an app called [PostMan](https://www.getpostman.com/downloads/) to test our API. 

Node.js comes with something called NPM (Node Package Manager), that we will use manage our node modules. After the install is complete, check that you have both Node.js and NPM by running these commands in your terminal:
```
node -v
npm -v
```
You should get a version back from each of these commands, if it was correctly installed.
OK, now let's create a folder and add some initial files by entering these commands in the terminal:
```
mkdir node-project
cd node-project
touch server.js middleware.js .gitignore
```
Next, we will initialize a package.json file, which will allow us to install and save node modules:
```
npm init -y
git init
```
Before we go any further, let's add this line to our `.gitignore` file so we don't track our `node_modules` if we are using git:
```
/node_modules
```
Alright, now we can install Express using npm. Enter this command in the terminal:`npm install express --save`

With that, your basic environment is set up. Check that you have these files:
```
-middleware.js
-node_modules
-.gitignore
-package-lock.json
-package.json
-server.js
```
Open your package.json file and make sure you have something like this under your dependencies:
```json
"dependencies": {
    "express": "^4.17.1",
  }
```
The number on the right is the version you downloaded. Since we aren't tracking the actual `node_modules` folder, this section is a reference used to re-install the modules your application depends on.
