## 📘 Section: Structs and Methods  
### 🔹 Category: Methods  
#### ✅ Answer 253: Methods with pointer receivers

A method with a pointer receiver can modify the struct's fields. Here, we define a `Counter` struct and an `Increment` method that increases its value.

```go
package main
import "fmt"

type Counter struct {
    Value int
}

func (c *Counter) Increment() {
    c.Value++
}

func main() {
    cnt := Counter{Value: 0}
    cnt.Increment()
    fmt.Println("Value:", cnt.Value)
}
```
