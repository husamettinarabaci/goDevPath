## 📘 Section: Concurrency II  
### 🔹 Category: Deadlocks and Race Conditions  
#### ✅ Answer 158: Deadlocks and race conditions

A deadlock occurs when goroutines wait on each other and cannot proceed. A race condition happens when multiple goroutines access shared data without synchronization.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    // Deadlock example
    ch1 := make(chan int)
    ch2 := make(chan int)
    go func() {
        ch1 <- 1 // waits for receiver
        <-ch2    // waits for value
    }()
    go func() {
        ch2 <- 2 // waits for receiver
        <-ch1    // waits for value
    }()
    // Uncommenting the following lines will cause a deadlock
    // time.Sleep(time.Second)

    // Race condition example
    var x int
    var wg sync.WaitGroup
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            x++ // not synchronized, causes race
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Race condition result:", x)
}
```
// To fix the deadlock, use buffered channels or proper synchronization.
// To fix the race condition, use a mutex or atomic operations.
