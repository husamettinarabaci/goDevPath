## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 47: Function that calls another function

This solution defines a function `double` that returns twice its input, and another function `printDouble` that calls `double` and prints the result. `printDouble` is called from `main`.

```go
package main
import "fmt"

func double(n int) int {
    return n * 2
}

func printDouble(n int) {
    result := double(n)
    fmt.Println("Double:", result)
}

func main() {
    printDouble(7)
}
```
