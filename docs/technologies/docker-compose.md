---
id: docker-compose
title: Docker Compose
sidebar_label: Docker Compose
slug: /docker-compose
---
## Deploy your apps using DPLYR and Docker Compose
<img class="right-image" src="https://cdn.rancher.com/wp-content/uploads/2016/04/20182217/compose.png" width="75px" height="75px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>

You need to configure your app to be ready for the deployment process. 

## Configuring App
### docker-compose.yml location
You need to set your docker-compose.yml at the main directory like this example
```
- docker-compose-app
     - docker-compose.yml
     - index.js
     - package.json
```