## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Variable Declaration and Initialization  
#### ✅ Answer 12: Declaring multiple variables at once

In Go, you can declare and initialize multiple variables in a single statement. Here is an example:

```go
package main
import "fmt"
func main() {
    var x, y int = 10, 20
    var name, age = "Bob", 30
    fmt.Println("x:", x, "y:", y)
    fmt.Println("name:", name, "age:", age)
}
```

This program demonstrates declaring multiple variables of the same and different types in one line, and printing their values.
