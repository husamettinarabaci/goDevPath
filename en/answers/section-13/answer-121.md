## 📘 Section: Packages and Imports  
### 🔹 Category: Creating and using packages  
#### ✅ Answer 121: Creating and using packages

In Go, you can organize code into packages for better modularity and reuse. To use a custom package, create a directory with a `.go` file, define exported functions, and import it in your `main` package.

Below is an example:

**greet/greet.go**
```go
package greet

func Hello() string {
    return "Hello from the greet package!"
}
```

**main.go**
```go
package main
import (
    "fmt"
    "greet"
)

func main() {
    fmt.Println(greet.Hello())
}
```

This example shows how to create a custom package (`greet`), define an exported function, and use it in the `main` package. Make sure the `greet` directory is at the same level as `main.go` or in your module's root.
