## 📘 Section: Control Flow  
### 🔹 Category: Switch Statements  
#### ✅ Answer 29: Using `fallthrough` in switch statements

The `fallthrough` statement in a `switch` block forces the execution to continue to the next case, even if its condition is not met.

```go
package main
import "fmt"

func main() {
    num := 1
    switch num {
    case 1:
        fmt.Println("Case 1")
        fallthrough
    case 2:
        fmt.Println("Case 2")
    default:
        fmt.Println("Default case")
    }
}
```
