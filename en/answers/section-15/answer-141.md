## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines, WaitGroup, channel usage  
#### ✅ Answer 141: Introduction to goroutines

A goroutine is a lightweight thread managed by the Go runtime. You can start a goroutine by using the `go` keyword before a function call. Use `time.Sleep` in `main` to give the goroutine time to complete.

```go
package main
import (
    "fmt"
    "time"
)

func sayHello() {
    fmt.Println("Hello from goroutine!")
}

func main() {
    go sayHello()
    time.Sleep(100 * time.Millisecond) // Give goroutine time to run
    fmt.Println("Main function done.")
}
```
