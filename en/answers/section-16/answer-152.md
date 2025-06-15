## 📘 Section: Concurrency II  
### 🔹 Category: Channel Directions and Synchronization  
#### ✅ Answer 152: Channel of channels

This example demonstrates how to use a channel of channels to coordinate communication between goroutines. Each inner channel carries an integer value.

```go
package main
import "fmt"

func main() {
    chOfCh := make(chan chan int)
    go func() {
        for i := 1; i <= 3; i++ {
            ch := make(chan int)
            chOfCh <- ch
            go func(val int, c chan int) {
                c <- val * 10
            }(i, ch)
        }
        close(chOfCh)
    }()
    for ch := range chOfCh {
        fmt.Println("Received:", <-ch)
    }
}
```
