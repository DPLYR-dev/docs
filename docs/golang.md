---
id: golang
title: Golang
sidebar_label: Golang
slug: /golang
---
## Deploy serious Golang apps using DPLYR 
<img class="right-image" src="https://camo.githubusercontent.com/98ed65187a84ecf897273d9fa18118ce45845057/68747470733a2f2f7261772e6769746875622e636f6d2f676f6c616e672d73616d706c65732f676f706865722d766563746f722f6d61737465722f676f706865722e706e67" width="50px" height="70px" />
<p>Are you ready to deploy your app on DPLYR Machines ?</p>

You need to configure your app to be ready for the deployment process. 

## Configuring App
### Renaming main file
You need to rename your main file to main.go and put your main.go file in a folder called src like this example
```
- go-app
    - test.go
     - src
        - main.go
```

### Setting database url
You need to set your database connection string as "127.0.0.1" instead of "localhost" to connect to your local database
```go
func main() {
  dsn := "user:pass@tcp(127.0.0.1:3306)/dbname?charset=utf8mb4&parseTime=True&loc=Local"
  db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
}
```

## Configuring Port
In your project when you start listening for connections set the port to the environment variable called PORT for example in an main.go app you can get port from env such as this code:
```go
package main

import (
  "fmt"
)
func main() {
   fmt.Println(os.Getenv("PORT"))
}
```