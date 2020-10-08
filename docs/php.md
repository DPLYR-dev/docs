---
id: php
title: PHP
sidebar_label: PHP
slug: /php
---
## Deploy amazing PHP apps using DPLYR 
<img class="right-image" src="https://newrelic.com/assets/pages/apm/php/php-elephant-logo-bd4f9d83be8c8563248fe4793f90bae7.png" width="85px" height="60px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>
You need to configure your app to be ready for the deployment process. 

## Configuring App

### App location
You need to set your project files at the main directory like this example
```
- php-app
     - index.php
     - index.html
```

## Setting database url
You need to set your database connection string as "127.0.0.1" instead of "localhost" to connect to your local database
```php
<?php
$databaseHost = '127.0.0.1';
$databaseName = 'dplyr';
$databaseUsername = 'dplyr';
$databasePassword = 'dplyr';
$mysqli = mysqli_connect($databaseHost, $databaseUsername, $databasePassword, $databaseName);
?>
```