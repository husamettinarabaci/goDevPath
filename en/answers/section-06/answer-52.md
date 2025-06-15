## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 52: Nested function calls

In Go, functions can call other functions and use their return values. Here, `outer` calls `inner` and prints the returned string.

```go
package main
import "fmt"

func inner() string {
    return "Hello from inner!"
}

func outer() {
    result := inner()
    fmt.Println(result)
}

func main() {
    outer()
}
```
