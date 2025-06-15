## 📘 Section: Concurrency II  
### 🔹 Category: Mutex and Synchronization  
#### ✅ Answer 153: Using `sync.Mutex` for mutual exclusion

To prevent race conditions when multiple goroutines access shared data, use a `sync.Mutex`. Lock the mutex before updating the shared variable and unlock it after. This ensures only one goroutine can modify the variable at a time.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var (
        mu sync.Mutex
        counter int
        wg sync.WaitGroup
    )
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            mu.Lock()
            counter++
            mu.Unlock()
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Final counter:", counter)
}
```
