## 📘 Section: Structs and Methods  
### 🔹 Category: Structs  
#### ✅ Answer 251: Defining structs and their fields

In Go, a struct is a composite type that groups together variables (fields) under a single type. Here, we define a `Person` struct with `Name` and `Age` fields, create an instance, and print its values.

```go
package main
import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{Name: "Alice", Age: 30}
    fmt.Println("Name:", p.Name)
    fmt.Println("Age:", p.Age)
}
```
