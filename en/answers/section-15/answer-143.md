## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines, WaitGroup, channel usage  
#### ✅ Answer 143: Synchronizing with `WaitGroup`

The `sync.WaitGroup` type allows you to wait for a collection of goroutines to finish. You increment the counter with `Add`, call `Done` in each goroutine, and call `Wait` in `main` to block until all are done.

```go
package main
import (
    "fmt"
    "sync"
)

func worker(id int, wg *sync.WaitGroup) {
    defer wg.Done()
    fmt.Printf("Worker %d done\n", id)
}

func main() {
    var wg sync.WaitGroup
    for i := 1; i <= 2; i++ {
        wg.Add(1)
        go worker(i, &wg)
    }
    wg.Wait()
    fmt.Println("All workers finished.")
}
```
