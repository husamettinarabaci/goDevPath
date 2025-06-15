## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines, WaitGroup, channel usage  
#### ✅ Answer 142: Launching a goroutine

You can launch a goroutine by prefixing a function call with the `go` keyword. This allows the function to run concurrently with the rest of your program.

```go
package main
import (
    "fmt"
    "time"
)

func worker() {
    fmt.Println("Worker goroutine started")
    time.Sleep(50 * time.Millisecond)
    fmt.Println("Worker goroutine finished")
}

func main() {
    go worker()
    fmt.Println("Main function continues...")
    time.Sleep(100 * time.Millisecond) // Wait for goroutine to finish
    fmt.Println("Main function done.")
}
```
