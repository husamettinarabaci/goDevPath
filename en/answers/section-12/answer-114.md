## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interfaces and Maps  
#### ✅ Answer 114: Interfaces and maps

In Go, maps can have interface types as their keys or values, allowing for flexible and dynamic data structures. However, when using interfaces as map keys, the underlying type must be comparable. The most common use is to have interface values as map values, enabling storage of different types that implement a shared interface.

Below is an example where an interface is used as the value type in a map:

```go
package main
import "fmt"

// Define an interface
type Shape interface {
    Area() float64
}

type Circle struct {
    Radius float64
}

func (c Circle) Area() float64 {
    return 3.14 * c.Radius * c.Radius
}

type Square struct {
    Side float64
}

func (s Square) Area() float64 {
    return s.Side * s.Side
}

func main() {
    // Map with string keys and Shape interface values
    shapes := make(map[string]Shape)
    shapes["circle"] = Circle{Radius: 2}
    shapes["square"] = Square{Side: 3}

    for name, shape := range shapes {
        fmt.Printf("%s area: %.2f\n", name, shape.Area())
    }
}
```

This example demonstrates how to use interfaces as map values, allowing different types that implement the `Shape` interface to be stored and accessed in a single map.
