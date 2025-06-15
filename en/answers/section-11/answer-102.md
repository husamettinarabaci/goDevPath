## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Methods  
#### ✅ Answer 102: Pointer vs value receivers

In Go, methods can have either value or pointer receivers. A value receiver gets a copy of the struct, so changes do not affect the original. A pointer receiver can modify the original struct. Example:

```go
package main
import "fmt"

type Counter struct {
    Value int
}

func (c Counter) IncrementByValue() {
    c.Value++
}

func (c *Counter) IncrementByPointer() {
    c.Value++
}

func main() {
    cnt := Counter{Value: 1}
    cnt.IncrementByValue()
    fmt.Println("After IncrementByValue:", cnt.Value) // 1
    cnt.IncrementByPointer()
    fmt.Println("After IncrementByPointer:", cnt.Value) // 2
}
```
