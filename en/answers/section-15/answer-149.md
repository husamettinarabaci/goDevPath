## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 149: Select statement basics

This example demonstrates how to use the `select` statement to receive from multiple channels. The program launches two goroutines that send values to two different channels after a delay, and the main function uses `select` to receive from whichever channel is ready first.

```go
package main
import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan int)
    ch2 := make(chan int)
    go func() {
        time.Sleep(100 * time.Millisecond)
        ch1 <- 1
    }()
    go func() {
        time.Sleep(200 * time.Millisecond)
        ch2 <- 2
    }()
    for i := 0; i < 2; i++ {
        select {
        case v := <-ch1:
            fmt.Println("Received", v, "from ch1")
        case v := <-ch2:
            fmt.Println("Received", v, "from ch2")
        }
    }
}
```
