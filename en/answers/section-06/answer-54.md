## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 54: Function that returns another function

In Go, functions can return other functions. This is useful for creating closures or configurable behaviors. Here, `makeGreeter` returns a function that prints a greeting.

```go
package main
import "fmt"

func makeGreeter() func() {
    return func() {
        fmt.Println("Hello from the greeter!")
    }
}

func main() {
    greeter := makeGreeter()
    greeter()
}
```
