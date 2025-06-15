## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 49: Function that returns a pointer

This solution defines a function `intPointer` that takes an integer and returns a pointer to it. The function is called from `main`, and the value pointed to by the returned pointer is printed.

```go
package main
import "fmt"

func intPointer(n int) *int {
    return &n
}

func main() {
    ptr := intPointer(42)
    fmt.Println("Value:", *ptr)
}
```
