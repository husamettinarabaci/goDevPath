## 📘 Section: Getting Started  
### 🔹 Category: main Function and Printing  
#### ✅ Answer 5: Converting number types using type conversion

This example demonstrates how to convert an integer to a float64 in Go using type conversion. Type conversion is done by specifying the target type in parentheses before the value.

```go
package main
import "fmt"

func main() {
    var i int = 42
    var f float64 = float64(i) // type conversion
    fmt.Println("Integer:", i)
    fmt.Println("Float64:", f)
}
```
