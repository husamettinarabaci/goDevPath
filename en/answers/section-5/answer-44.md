## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 44: Function returning multiple values

This solution defines a function named `sumAndProduct` that takes two integers and returns both their sum and product. The function is called from `main`, and both results are printed to the terminal.

```go
package main
import "fmt"

func sumAndProduct(a int, b int) (int, int) {
    return a + b, a * b
}

func main() {
    sum, product := sumAndProduct(4, 6)
    fmt.Println("Sum:", sum)
    fmt.Println("Product:", product)
}
```
