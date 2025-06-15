## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ✅ Answer 156: Using `sync.Cond`

`sync.Cond` allows goroutines to wait for or signal a condition. It's useful for coordinating access to shared resources.

```go
package main
import (
    "fmt"
    "sync"
    "time"
)

func main() {
    var (
        mu sync.Mutex
        cond = sync.NewCond(&mu)
        queue []int
    )

    // Consumer goroutine
    go func() {
        mu.Lock()
        for len(queue) == 0 {
            cond.Wait()
        }
        fmt.Println("Consumed:", queue[0])
        queue = queue[1:]
        mu.Unlock()
    }()

    // Producer goroutine
    time.Sleep(100 * time.Millisecond)
    mu.Lock()
    queue = append(queue, 42)
    cond.Signal()
    mu.Unlock()

    time.Sleep(200 * time.Millisecond)
}
```
