## 📘 Section: Structs  
### 🔹 Category: Structs with Methods  
#### ✅ Answer 77: Structs with methods

You can define methods on structs in Go by using a receiver. This allows you to associate behavior with data types.

```go
package main
import "fmt"

type Rectangle struct {
    width, height float64
}

func (r Rectangle) Area() float64 {
    return r.width * r.height
}

func main() {
    rect := Rectangle{width: 5, height: 3}
    fmt.Println("Area:", rect.Area())
}
```
