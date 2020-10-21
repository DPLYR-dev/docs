---
id: nodejs
title: Node.js
sidebar_label: Node.js
slug: /nodejs
---
## Deploy amazing Node.JS apps using DPLYR 
<img class="right-image" src="https://www.tipstoremember.com/wp-content/uploads/2017/09/nodejs_logo.png" width="70px" height="70px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>
You need to configure your app to be ready for the deployment process. 

## Configuring **App**

### package.json location
You need to set your package.json at the main directory like this example
```
- node-app
     - package.json
     - src
        - index.js
```

### Add npm start command to package.json
You need to add start command to your scripts in package.json
```json
{
  "name": "node-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node src/index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
}
```
:::caution

If you are using ** nodemon ** in development please be sure that you didn't forgot to add ** nodemon ** into * dependencies * or * devDependencies *

:::
## Configuring Port
In your project when you start listening for connections set the port to the environment variable called PORT for example in an express.js app you will do this:
```js
const express = require('express');
const app = express();

app.get('*', function(req, res) {
  res.json({"message":"Hello World"});
});

const PORT = process.env.PORT || 3000; // 3000 can be whatever port you want to use in your development computer 

app.listen(PORT, function () {
  console.log('App is running!');
});
```