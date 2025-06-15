## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointer Usage, new/make, Struct Pointers  
#### ✅ Answer 62: Passing pointers to functions

In Go, you can pass a pointer to a function to allow the function to modify the original variable. The function receives the address of the variable and can change its value using dereferencing.

```go
package main
import "fmt"

func increment(p *int) {
    *p = *p + 1
}

func main() {
    x := 5
    increment(&x)
    fmt.Println("x after increment:", x) // Output: 6
}
```

Here, the `increment` function takes a pointer to an integer and increases the value at that address. The change is reflected in the original variable.
