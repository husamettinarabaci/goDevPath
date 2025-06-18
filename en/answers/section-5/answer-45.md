## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 45: Function with named return values

This solution defines a function named `sumAndDiff` that uses named return values to return the sum and difference of two integers. The function is called from `main`, and both results are printed to the terminal.

```go
package main
import "fmt"

func sumAndDiff(a int, b int) (sum int, diff int) {
    sum = a + b
    diff = a - b
    return
}

func main() {
    s, d := sumAndDiff(10, 4)
    fmt.Println("Sum:", s)
    fmt.Println("Difference:", d)
}
```
