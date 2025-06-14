## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Zero Values  
#### ✅ Answer 18: Zero values in Go

In Go, variables that are declared but not explicitly initialized are given default values called zero values. Each type has its own zero value:
- `int`: 0
- `float64`: 0.0
- `string`: ""
- `bool`: false

Here is an example:

```go
package main
import "fmt"

func main() {
    var a int
    var b float64
    var c string
    var d bool
    fmt.Println(a) // 0
    fmt.Println(b) // 0
    fmt.Println(c) // ""
    fmt.Println(d) // false
}
```
