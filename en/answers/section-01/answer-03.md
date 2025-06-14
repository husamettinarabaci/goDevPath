## 📘 Section: Getting Started  
### 🔹 Category: main Function and Printing  
#### ✅ Answer 3: Difference between `var` and `const` in Go

This example demonstrates the difference between variables and constants in Go. Variables declared with `var` can be reassigned, while constants declared with `const` cannot be changed after their initial assignment.

```go
package main
import "fmt"

func main() {
    var x = 10 // variable: can be changed
    const y = 5 // constant: cannot be changed
    fmt.Println("Variable x:", x)
    fmt.Println("Constant y:", y)
}
```
