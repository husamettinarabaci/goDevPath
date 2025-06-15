## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 147: Closing channels

This example shows how to close a channel and detect its closure using the `close` function and the "comma ok" idiom. Receivers can use the second value from a receive operation to check if the channel is closed.

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
    for {
        val, ok := <-ch
        if !ok {
            fmt.Println("Channel closed")
            break
        }
        fmt.Println("Received:", val)
    }
}
```
