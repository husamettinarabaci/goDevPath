## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Type Conversion  
#### ✅ Answer 19: Type conversion between numeric types

In Go, you can convert between numeric types using explicit type conversion. Here is an example:

```go
package main
import "fmt"

func main() {
    var a int = 42
    var b float64 = float64(a)
    fmt.Println(b) // 42.0
    var c int = int(b)
    fmt.Println(c) // 42
}
```
