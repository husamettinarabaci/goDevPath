## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 148: Range over channels

This example shows how to use a `range` loop to receive values from a channel until it is closed. The loop automatically exits when the channel is closed.

```go
package main
import "fmt"

func main() {
    ch := make(chan int)
    go func() {
        for i := 1; i <= 3; i++ {
            ch <- i
        }
        close(ch)
    }()
    for val := range ch {
        fmt.Println("Received:", val)
    }
    fmt.Println("Channel closed, done receiving.")
}
```
