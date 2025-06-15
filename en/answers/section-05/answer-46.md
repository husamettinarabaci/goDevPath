## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 46: Function with variadic parameters

This solution defines a function named `sumAll` that uses variadic parameters to accept any number of integers and returns their sum. The function is called from `main` with different argument counts, and the results are printed.

```go
package main
import "fmt"

func sumAll(nums ...int) int {
    sum := 0
    for _, n := range nums {
        sum += n
    }
    return sum
}

func main() {
    fmt.Println("Sum 1:", sumAll(1, 2, 3))
    fmt.Println("Sum 2:", sumAll(5, 10, 15, 20))
}
```
