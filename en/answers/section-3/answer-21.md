## 📘 Section: Control Flow  
### 🔹 Category: If/Else Statements  
#### ✅ Answer 21: Using `if`, `else if`, and `else`

In Go, `if`, `else if`, and `else` statements are used to control the flow of a program based on conditions. Here is an example:

```go
package main
import "fmt"

func main() {
    var num int = -5
    if num > 0 {
        fmt.Println("Positive number")
    } else if num == 0 {
        fmt.Println("Zero")
    } else {
        fmt.Println("Negative number")
    }
}
```
