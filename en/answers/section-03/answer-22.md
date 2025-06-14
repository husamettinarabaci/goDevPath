## 📘 Section: Control Flow  
### 🔹 Category: Switch Statements  
#### ✅ Answer 22: Using `switch` statements

In Go, a `switch` statement allows you to execute different code blocks based on the value of a variable. Here is an example:

```go
package main
import "fmt"

func main() {
    var num int = 2
    switch num {
    case 1:
        fmt.Println("One")
    case 2:
        fmt.Println("Two")
    case 3:
        fmt.Println("Three")
    default:
        fmt.Println("Other value")
    }
}
```
