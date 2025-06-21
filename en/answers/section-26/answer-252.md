## 📘 Section: Structs and Methods  
### 🔹 Category: Methods  
#### ✅ Answer 252: Creating methods with value receivers

A method with a value receiver operates on a copy of the struct. Here, we define a `Rectangle` struct and an `Area` method that calculates the area.

```go
package main
import "fmt"

type Rectangle struct {
    Width, Height float64
}

func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func main() {
    rect := Rectangle{Width: 5, Height: 3}
    fmt.Println("Area:", rect.Area())
}
```
