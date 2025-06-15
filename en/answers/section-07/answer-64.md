## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointer Usage, new/make, Struct Pointers  
#### ✅ Answer 64: Nil pointers and zero values

In Go, a pointer that is declared but not initialized has the zero value `nil`. You should always check if a pointer is nil before dereferencing it to avoid a runtime panic.

```go
package main
import "fmt"

func main() {
    var p *int // nil pointer
    fmt.Println("Pointer value:", p) // Output: <nil>

    if p != nil {
        fmt.Println(*p)
    } else {
        fmt.Println("Pointer is nil, cannot dereference.")
    }
}
```

Dereferencing a nil pointer will cause a runtime panic. Always check for nil before using a pointer.
