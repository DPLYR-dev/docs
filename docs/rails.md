---
id: rails
title: Ruby on Rails
sidebar_label: Ruby on Rails
slug: /ruby-on-rails
---
## Deploy Ruby On Rails backends and apps using DPLYR 
<img class="right-image" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/1200px-Ruby_On_Rails_Logo.svg.png" width="90px"  />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>

You need to configure your app to be ready for the deployment process. 

## Configuring App
### Gemfile location
You need to set your Gemfile at the main directory like this example
```
- ruby-app
     - Gemfile
     - Rakefile
     - config.ru
     - README.md
     - app
     - lib
     - bin
```

### Setting database url
You need to set your database connection string as "127.0.0.1" instead of "localhost" in config/database.yml to connect to your local database
```yaml
development:
  url: postgresql://127.0.0.1/databaseName?pool=5
```

