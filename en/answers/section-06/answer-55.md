## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 55: Passing functions as arguments

In Go, you can pass functions as arguments to other functions. Here, `operate` takes a function and applies it to two integers.

```go
package main
import "fmt"

func operate(a, b int, fn func(int, int) int) int {
    return fn(a, b)
}

func add(x, y int) int {
    return x + y
}

func multiply(x, y int) int {
    return x * y
}

func main() {
    fmt.Println(operate(3, 4, add))      // Output: 7
    fmt.Println(operate(3, 4, multiply)) // Output: 12
}
```
