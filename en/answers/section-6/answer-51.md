## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 51: Function scope and variable lifetime

Variables declared inside a function in Go are only accessible within that function. Their lifetime is limited to the function's execution. Trying to access them outside results in a compile-time error.

```go
package main
import "fmt"

func showScope() {
    x := 42
    fmt.Println(x) // OK: x is accessible here
}

func main() {
    showScope()
    // fmt.Println(x) // ERROR: x is not defined in this scope
}
```
