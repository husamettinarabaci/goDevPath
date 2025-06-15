## 📘 Section: Advanced Go Features  
### 🔹 Category: Context and Cancellation  
#### ✅ Answer 209: Using context for cancellation

The `context` package in Go provides a way to signal cancellation to goroutines and manage their lifetimes. `context.WithCancel` returns a context and a cancel function. When the cancel function is called, any goroutine using that context can detect the cancellation and stop its work.

Here's an example that demonstrates cancellation of a long-running task:

```go
package main
import (
    "context"
    "fmt"
    "time"
)

func longTask(ctx context.Context) {
    fmt.Println("Task started")
    for i := 1; ; i++ {
        select {
        case <-ctx.Done():
            fmt.Println("Task cancelled!")
            return
        default:
            fmt.Printf("Working... step %d\n", i)
            time.Sleep(500 * time.Millisecond)
        }
    }
}

func main() {
    ctx, cancel := context.WithCancel(context.Background())
    go longTask(ctx)
    time.Sleep(2 * time.Second) // Let the task run for a while
    cancel() // Cancel the task
    time.Sleep(1 * time.Second) // Wait to see cancellation message
}
```
