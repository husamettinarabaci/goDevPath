## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 42: Function with parameters and return value

This solution defines a function named `add` that takes two integers as parameters and returns their sum. The function is called from `main`, and the result is printed to the terminal.

```go
package main
import "fmt"

func add(a int, b int) int {
    return a + b
}

func main() {
    result := add(3, 5)
    fmt.Println("Sum:", result)
}
```
