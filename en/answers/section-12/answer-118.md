## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Comparing interface values  
#### ✅ Answer 118: Comparing interface values

In Go, interface values are equal if their dynamic types and dynamic values are both equal. If the underlying types differ, the comparison returns false. If both are nil, the comparison returns true.

Below is an example:

```go
package main
import "fmt"

type Shape interface {
    Area() float64
}

type Circle struct {
    R float64
}

func (c Circle) Area() float64 {
    return 3.14 * c.R * c.R
}

type Square struct {
    S float64
}

func (s Square) Area() float64 {
    return s.S * s.S
}

func main() {
    var a, b Shape
    a = Circle{R: 2}
    b = Circle{R: 2}
    fmt.Println("a == b:", a == b) // true, same type and value

    b = Circle{R: 3}
    fmt.Println("a == b:", a == b) // false, different value

    b = Square{S: 2}
    fmt.Println("a == b:", a == b) // false, different type

    var c Shape
    var d Shape
    fmt.Println("c == d:", c == d) // true, both nil
}
```

This example demonstrates how interface values are compared in Go, including cases with different types, values, and nil interfaces.
