## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointer Usage, new/make, Struct Pointers  
#### ✅ Answer 61: Declaring and using pointers

In Go, a pointer holds the memory address of a variable. You can declare a pointer using the `*` operator and assign it the address of a variable using `&`. Dereferencing a pointer with `*` gives you access to the value stored at that address.

```go
package main
import "fmt"

func main() {
    var x int = 10
    var p *int = &x

    fmt.Println("Value of x:", x)
    fmt.Println("Value via pointer:", *p)
}
```

This program declares an integer variable and a pointer to it, then prints the value using both the variable and the pointer.
