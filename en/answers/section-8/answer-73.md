## 📘 Section: Structs  
### 🔹 Category: Struct with multiple field types  
#### ✅ Answer 73: Struct with multiple field types

A struct in Go can have fields of different types. Here, we define a `Product` struct with string, float64, and bool fields, create an instance, and print it.

```go
package main
import "fmt"

type Product struct {
    name    string
    price   float64
    inStock bool
}

func main() {
    p := Product{"Laptop", 1299.99, true}
    fmt.Println(p)
}
```
