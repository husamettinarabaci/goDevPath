## 📘 Section: Concurrency II  
### 🔹 Category: Deadlocks and Race Conditions  
#### ✅ Answer 159: Detecting race conditions with `-race`

The `-race` flag enables the Go race detector, which reports data races at runtime. Here's an example of a race condition and how to detect it.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var x int
    var wg sync.WaitGroup
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            x++ // race condition
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Final value:", x)
}
```

To detect the race, run:

```
go run -race main.go
```

To fix the race, use a mutex:

```go
var mu sync.Mutex
...
go func() {
    mu.Lock()
    x++
    mu.Unlock()
    wg.Done()
}()
```
