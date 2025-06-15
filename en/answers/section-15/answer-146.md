## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 146: Buffered vs unbuffered channels

Unbuffered channels require both sender and receiver to be ready at the same time, while buffered channels allow sending up to their capacity without a receiver. This example demonstrates both behaviors.

```go
package main
import "fmt"

func main() {
    // Unbuffered channel
    unbuf := make(chan int)
    go func() {
        unbuf <- 1
        fmt.Println("Sent on unbuffered channel")
    }()
    val := <-unbuf
    fmt.Println("Received from unbuffered channel:", val)

    // Buffered channel
    buf := make(chan int, 2)
    buf <- 10
    fmt.Println("Sent first to buffered channel")
    buf <- 20
    fmt.Println("Sent second to buffered channel")
    fmt.Println("Received from buffered channel:", <-buf)
    fmt.Println("Received from buffered channel:", <-buf)
}
```
