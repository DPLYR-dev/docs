---
id: python
title: Python
sidebar_label: Python
slug: /python
---
## Deploy fastest Python apps using DPLYR 
<img class="right-image" src="https://insidehpc.com/wp-content/uploads/2016/01/Python-logo-notext.svg_.png" width="70px" height="70px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>
You need to configure your app to be ready for the deployment process. 

## What is the Procfile?
Procfile is a mechanism for declaring what commands are run by your application on the cloud platforms.

But basically you use the Procfile to tell the cloud platforms how to run your app. The part to the left of the colon on each line is the process type; the part on the right is the command to run to start that process.

*Example*

```
web: YOUR RUN COMMAND
```

## Configuring App

### Configure requirements.txt

** 1. ** You need to create a requirements.txt file and fill it with your packages/dependencies names like this example
```
matplotlib==3.1.3
Pyrebase4==4.3.0
scipy==1.4.1
xlrd==1.2.0
plotly==4.9.0
dash_core_components==1.10.2
dash==1.14.0
xgboost==1.2.0
dash_table==4.9.0
firebase_admin==4.3.0
pandas==1.0.1
numpy==1.18.1
dash_html_components==1.0.3
pyrebase==3.0.27
scikit_learn==0.23.2
```

** 2. ** You need to set your requirements.txt at the main directory like this example
```
- python-app
     - requirements.txt
     - src
        - index.py
```

### Configure Procfile

What is the ** * [Procfile](#what-is-the-procfile "Procfile") * ** ?

** 1. ** You need to create a Procfile and set your run command like this example
```
web: gunicorn app:server --bind 0.0.0.0:8000
```

** 2. ** You need to set your Procfile at the main directory like this example

```
- python-app
     - Procfile
     - src
        - index.py
```


### Setting database url
You need to set your database connection string as "127.0.0.1" instead of "localhost" to connect to your local database
```python
from flask import Flask, render_template, request, redirect, url_for, flash
from flask_mysqldb import MySQL
app = Flask(__name__)
app.secret_key = 'many random bytes'
app.config['MYSQL_HOST'] = '127.0.0.1'
app.config['MYSQL_USER'] = 'dplyr'
app.config['MYSQL_PASSWORD'] = 'dplyr'
app.config['MYSQL_DB'] = 'dplyr'
mysql = MySQL(app)
```

