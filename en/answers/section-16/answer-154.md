## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ✅ Answer 154: Using `sync.RWMutex`

`sync.RWMutex` allows multiple goroutines to read shared data simultaneously, but only one to write at a time. Use `RLock`/`RUnlock` for readers and `Lock`/`Unlock` for writers.

```go
package main
import (
    "fmt"
    "sync"
    "time"
)

func main() {
    var (
        rw sync.RWMutex
        counter int
        wg sync.WaitGroup
    )
    // Writers
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func() {
            rw.Lock()
            counter++
            rw.Unlock()
            wg.Done()
        }()
    }
    // Readers
    for i := 0; i < 10; i++ {
        wg.Add(1)
        go func() {
            rw.RLock()
            _ = counter // simulate read
            time.Sleep(10 * time.Millisecond)
            rw.RUnlock()
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Final counter:", counter)
}
```
