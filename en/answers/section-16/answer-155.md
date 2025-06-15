## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ✅ Answer 155: Using `sync.Once`

`sync.Once` provides a way to ensure a function is executed only once, even if called from multiple goroutines. This is useful for one-time initialization.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var once sync.Once
    var wg sync.WaitGroup

    initialize := func() {
        fmt.Println("Initialized!")
    }

    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func() {
            once.Do(initialize)
            wg.Done()
        }()
    }
    wg.Wait()
}
```
