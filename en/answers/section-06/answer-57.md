## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 57: Recursion in Go functions

Recursion is when a function calls itself to solve a problem. Here, the `factorial` function calls itself to compute the factorial of a number.

```go
package main
import "fmt"

func factorial(n int) int {
    if n == 0 {
        return 1
    }
    return n * factorial(n-1)
}

func main() {
    fmt.Println(factorial(5)) // Output: 120
}
```
