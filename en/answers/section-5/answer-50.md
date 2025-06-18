## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Parameters  
#### ✅ Answer 50: Function that takes a pointer as argument

To modify a variable's value inside a function, you can pass a pointer to that variable. The function can then dereference the pointer and change the value at that memory address.

```go
package main
import "fmt"

func increment(num *int) {
    *num = *num + 1
}

func main() {
    x := 10
    increment(&x)
    fmt.Println(x) // Output: 11
}
```
