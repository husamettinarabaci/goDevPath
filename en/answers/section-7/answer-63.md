## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointer Usage, new/make, Struct Pointers  
#### ✅ Answer 63: Returning pointers from functions

In Go, you can return a pointer to a local variable from a function. Go's memory management ensures the variable remains valid as long as it is referenced.

```go
package main
import "fmt"

func newInt() *int {
    x := 42
    return &x
}

func main() {
    p := newInt()
    fmt.Println("Value from pointer:", *p) // Output: 42
}
```

Here, `newInt` returns a pointer to a local variable, and the value is accessed in `main` using the returned pointer.
