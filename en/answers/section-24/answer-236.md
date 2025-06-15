## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Using context for timeouts  
#### ✅ Answer 236: Using context for timeouts

The `context.WithTimeout` function allows you to automatically cancel an operation if it takes too long. In this example, a long-running task is started in a goroutine. If the task finishes before the timeout, its result is printed. If the timeout occurs first, the context is canceled and a timeout message is shown.

```go
package main

import (
    "context"
    "fmt"
    "time"
)

func longOperation(ctx context.Context) error {
    select {
    case <-time.After(3 * time.Second):
        return nil // Simulate work done
    case <-ctx.Done():
        return ctx.Err()
    }
}

func main() {
    ctx, cancel := context.WithTimeout(context.Background(), 2*time.Second)
    defer cancel()

    err := longOperation(ctx)
    if err != nil {
        fmt.Println("Operation failed:", err)
    } else {
        fmt.Println("Operation completed successfully")
    }
}
```
