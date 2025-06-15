## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ✅ Answer 157: Using `sync.Map`

`sync.Map` provides a concurrent map implementation that is safe for multiple goroutines to use without explicit locking.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var m sync.Map
    var wg sync.WaitGroup

    // Writer goroutines
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(i int) {
            m.Store(i, i*i)
            wg.Done()
        }(i)
    }

    // Reader goroutines
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(i int) {
            if v, ok := m.Load(i); ok {
                fmt.Printf("Key: %d, Value: %v\n", i, v)
            }
            wg.Done()
        }(i)
    }

    wg.Wait()

    // Print all contents
    m.Range(func(key, value any) bool {
        fmt.Printf("%v: %v\n", key, value)
        return true
    })
}
```
