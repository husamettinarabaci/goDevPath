## 📘 Section: Structs  
### 🔹 Category: Comparing Structs  
#### ✅ Answer 79: Comparing structs

In Go, you can compare structs for equality if all their fields are comparable. The comparison checks if all corresponding fields are equal.

```go
package main
import "fmt"

type Point struct {
    x, y int
}

func main() {
    p1 := Point{x: 1, y: 2}
    p2 := Point{x: 1, y: 2}
    p3 := Point{x: 2, y: 3}
    fmt.Println("p1 == p2:", p1 == p2) // true
    fmt.Println("p1 == p3:", p1 == p3) // false
}
```
