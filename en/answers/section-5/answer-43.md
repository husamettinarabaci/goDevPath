## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 43: Calling a function from `main`

This solution defines a function named `greet` that prints a message. The `main` function calls `greet`, demonstrating how to invoke a user-defined function in Go.

```go
package main
import "fmt"

func greet() {
    fmt.Println("Hello from function!")
}

func main() {
    greet()
}
```
