## 📘 Section: Structs and Methods  
### 🔹 Category: Interfaces and Polymorphism  
#### ✅ Answer 270: Using interfaces to achieve polymorphism

Interfaces in Go allow different types to be treated uniformly. Here, both `Circle` and `Rectangle` implement the `Shape` interface, enabling polymorphic behavior.

```go
package main
import (
    "fmt"
    "math"
)

type Shape interface {
    Area() float64
}

type Circle struct {
    Radius float64
}

type Rectangle struct {
    Width, Height float64
}

func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func printArea(s Shape) {
    fmt.Printf("Area: %.2f\n", s.Area())
}

func main() {
    c := Circle{Radius: 2.5}
    r := Rectangle{Width: 4, Height: 3}
    printArea(c)
    printArea(r)
}
```
