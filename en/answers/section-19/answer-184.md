## 📘 Section: Standard Library Essentials  
### 🔹 Category: math Package  
#### ✅ Answer 184: Using the `math` package

The `math` package in Go provides basic constants and mathematical functions. Here, we use `math.Sqrt` to calculate the square root of 16 and `math.Pi` to get the value of Pi.

```go
package main
import (
    "fmt"
    "math"
)

func main() {
    sqrt := math.Sqrt(16)
    pi := math.Pi
    fmt.Println("Square root of 16:", sqrt)
    fmt.Println("Value of Pi:", pi)
}
```
