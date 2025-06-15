## 📘 Section: Pointers and Memory  
### 🔹 Category: Dereferencing pointers  
#### ✅ Answer 70: Dereferencing pointers

Dereferencing a pointer means accessing the value stored at the memory address the pointer refers to. Here, we use the `*` operator to assign and read the value via the pointer.

```go
package main
import "fmt"

func main() {
    var x int
    p := &x        // pointer to x
    *p = 42        // assign value via pointer
    fmt.Println(x) // prints: 42
    fmt.Println(*p) // prints: 42
}
```
