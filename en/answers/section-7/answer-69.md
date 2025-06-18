## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointers to structs  
#### ✅ Answer 69: Pointers to structs

Pointers to structs allow you to modify the fields of a struct via its address. Here, we define a `Person` struct, create a pointer to it, and update its fields using the pointer.

```go
package main
import "fmt"

type Person struct {
    name string
    age  int
}

func main() {
    p := Person{"Alice", 30}
    fmt.Println(p) // before modification

    ptr := &p
    ptr.name = "Bob"
    ptr.age = 40

    fmt.Println(p) // after modification
}
```
