## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 56: Using closures in Go

A closure in Go is a function value that references variables from outside its body. The function may access and modify these variables even after the outer function has finished executing. Here, `makeCounter` returns a closure that increments and returns a counter.

```go
package main
import "fmt"

func makeCounter() func() int {
    count := 0
    return func() int {
        count++
        return count
    }
}

func main() {
    counter := makeCounter()
    fmt.Println(counter()) // Output: 1
    fmt.Println(counter()) // Output: 2
    fmt.Println(counter()) // Output: 3
}
```
