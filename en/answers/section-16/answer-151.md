## 📘 Section: Concurrency II  
### 🔹 Category: Channel Directions and Synchronization  
#### ✅ Answer 151: Channel directions (send-only, receive-only)

This example shows how to use channel direction types to restrict functions to sending or receiving only. The `chan<- int` type is send-only, and `<-chan int` is receive-only.

```go
package main
import "fmt"

func send(ch chan<- int) {
    ch <- 42
}

func receive(ch <-chan int) {
    val := <-ch
    fmt.Println("Received:", val)
}

func main() {
    ch := make(chan int)
    go send(ch)
    go receive(ch)
    // Wait for goroutines to finish (simple sleep for demo)
    // In production, use sync.WaitGroup
    select {}
}
```
