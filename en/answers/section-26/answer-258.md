## 📘 Section: Structs and Methods  
### 🔹 Category: Struct Comparison  
#### ✅ Answer 258: Struct equality and comparison

Structs in Go can be compared for equality if all their fields are comparable. Here, two `Point` structs are compared using the `==` operator.

```go
package main
import "fmt"

type Point struct {
    X, Y int
}

func main() {
    p1 := Point{X: 1, Y: 2}
    p2 := Point{X: 1, Y: 2}
    if p1 == p2 {
        fmt.Println("Points are equal")
    } else {
        fmt.Println("Points are not equal")
    }
}
```
