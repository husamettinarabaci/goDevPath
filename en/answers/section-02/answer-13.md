## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Constants and iota  
#### ✅ Answer 13: Defining constants and using `iota`

In Go, constants are declared with the `const` keyword. The `iota` identifier is used within a constant block to generate sequential values automatically. Here is an example:

```go
package main
import "fmt"
func main() {
    const Pi = 3.14
    const (
        A = iota // 0
        B        // 1
        C        // 2
    )
    fmt.Println("Pi:", Pi)
    fmt.Println("A:", A, "B:", B, "C:", C)
}
```

This program demonstrates defining a constant and using `iota` to create a sequence of constants.
