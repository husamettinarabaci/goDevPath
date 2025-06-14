## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Type Inference  
#### ✅ Answer 15: Type inference in variable declarations

Go can infer the type of a variable from the value assigned to it. You do not need to specify the type explicitly. Here is an example:

```go
package main
import "fmt"
func main() {
    name := "Charlie"   // inferred as string
    age := 22           // inferred as int
    pi := 3.1415        // inferred as float64
    fmt.Printf("name: %v (%T)\n", name, name)
    fmt.Printf("age: %v (%T)\n", age, age)
    fmt.Printf("pi: %v (%T)\n", pi, pi)
}
```

This program demonstrates type inference using the short variable declaration syntax (`:=`).
