## 📘 Section: Packages and Imports  
### 🔹 Category: Organizing Code  
#### ✅ Answer 130: Organizing code with packages

Organizing code into packages improves modularity and maintainability. In Go, you can create separate folders for each package. For example:

`utils/utils.go`:
```go
package utils

// Greet returns a greeting message.
func Greet(name string) string {
    return "Hello, " + name
}
```

`main.go`:
```go
package main

import (
    "fmt"
    "yourmodule/utils"
)

func main() {
    msg := utils.Greet("GoDevPath")
    fmt.Println(msg)
}
```

Replace `yourmodule` with your actual module name. This structure allows you to reuse code and keep your project organized.
