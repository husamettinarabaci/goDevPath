## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines, WaitGroup, channel usage  
#### ✅ Answer 144: Using channels for communication

Channels provide a way for goroutines to communicate safely. You can send a value from one goroutine and receive it in another.

```go
package main
import "fmt"

func sendValue(ch chan int) {
    ch <- 42
}

func main() {
    ch := make(chan int)
    go sendValue(ch)
    value := <-ch
    fmt.Println("Received:", value)
}
```
