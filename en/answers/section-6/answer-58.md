## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, Recursion, Defer, Panic/Recover  
#### ✅ Answer 58: Defer statements in functions

The `defer` statement in Go schedules a function call to run after the surrounding function returns. Deferred calls are executed in last-in, first-out order. In this example, the deferred print statement runs after the rest of the function completes, just before the function actually returns.

```go
package main
import "fmt"

func showDefer() {
    fmt.Println("Before defer")
    defer fmt.Println("This is deferred and runs last!")
    fmt.Println("After defer, but before function ends")
}

func main() {
    showDefer()
}
```
