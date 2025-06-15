## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, Recursion, Defer, Panic/Recover  
#### ✅ Answer 59: Panic and recover in functions

In Go, `panic` is used to indicate a serious error, and `recover` can be used to regain control of a panicking goroutine. By using `defer`, you can call `recover` to handle the panic and prevent the program from crashing.

```go
package main
import "fmt"

func safeDivide(a, b int) {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered from panic:", r)
        }
    }()
    if b == 0 {
        panic("division by zero")
    }
    fmt.Println("Result:", a/b)
}

func main() {
    safeDivide(10, 0)
    fmt.Println("Program continues after recover.")
}
```

This example triggers a panic when dividing by zero, but `recover` catches it and allows the program to continue.
