## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Methods  
#### ✅ Answer 103: Method chaining

Method chaining in Go is achieved by having methods with pointer receivers return the struct pointer, allowing multiple calls in a single statement. Example:

```go
package main
import "fmt"

type Counter struct {
    Value int
}

func (c *Counter) Add(n int) *Counter {
    c.Value += n
    return c
}

func (c *Counter) Multiply(n int) *Counter {
    c.Value *= n
    return c
}

func main() {
    cnt := &Counter{}
    cnt.Add(2).Multiply(5)
    fmt.Println(cnt.Value) // 10
}
```
