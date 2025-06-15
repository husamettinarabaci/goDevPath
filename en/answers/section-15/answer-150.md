## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ✅ Answer 150: Timeout with `select` and `time.After`

This example shows how to use `select` and `time.After` to implement a timeout when waiting for a value from a channel. If the channel does not send a value within the timeout, a timeout message is printed.

```go
package main
import (
    "fmt"
    "time"
)

func main() {
    ch := make(chan int)
    select {
    case v := <-ch:
        fmt.Println("Received:", v)
    case <-time.After(1 * time.Second):
        fmt.Println("Timeout: no value received")
    }
}
```
