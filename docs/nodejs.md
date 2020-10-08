---
id: nodejs
title: Node.js
sidebar_label: Node.js
slug: /nodejs
---
## Deploy amazing Node.JS apps using DPLYR 
<img class="right-image" src="https://camo.githubusercontent.com/98ed65187a84ecf897273d9fa18118ce45845057/68747470733a2f2f7261772e6769746875622e636f6d2f676f6c616e672d73616d706c65732f676f706865722d766563746f722f6d61737465722f676f706865722e706e67" width="50px" height="70px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>
You need to configure your app to be ready for the deployment process. 

## Configuring App

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

If you are using nodemon in development so please be sure that you didn't forgot to add nodemon into dependencies or devDependencies

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