## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 145: Sending and receiving on channels

This example shows how to use channels for communication between goroutines. The main goroutine creates a channel of type `int`, starts a new goroutine to send a value, and then receives and prints that value.

```go
package main
import (
    "fmt"
)

func main() {
    ch := make(chan int)
    go func() {
        ch <- 42
    }()
    value := <-ch
    fmt.Println(value)
}
```
