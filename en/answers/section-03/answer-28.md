## 📘 Section: Control Flow  
### 🔹 Category: Switch Statements  
#### ✅ Answer 28: Using `switch` with multiple cases

You can group multiple case values in a single case block in a `switch` statement. This allows you to handle several values with the same code.

```go
package main
import "fmt"

func main() {
    num := 2
    switch num {
    case 1, 2, 3:
        fmt.Println("num is 1, 2, or 3")
    case 4, 5:
        fmt.Println("num is 4 or 5")
    default:
        fmt.Println("num is something else")
    }
}
```
