## 📘 Section: Error Handling  
### 🔹 Category: Handling errors with panic and recover  
#### ✅ Answer 136: Handling errors with `panic` and `recover`

`panic` and `recover` are used for handling unexpected errors in Go. `panic` stops normal execution, and `recover` can catch the panic in a deferred function.

```go
package main

import "fmt"

func mayPanic(n int) {
    if n < 0 {
        panic("negative value not allowed")
    }
    fmt.Println("Value:", n)
}

func safeCall(n int) {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered from panic:", r)
        }
    }()
    mayPanic(n)
    fmt.Println("Function completed normally.")
}

func main() {
    safeCall(5)
    safeCall(-2)
}
```

This example shows how to use `panic` and `recover` for error handling in Go.
