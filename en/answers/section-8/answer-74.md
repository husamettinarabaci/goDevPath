## 📘 Section: Structs  
### 🔹 Category: Struct Embedding and Composition  
#### ✅ Answer 74: Struct embedding (composition)

Struct embedding (composition) allows you to build complex types from simpler ones. Here, `Employee` embeds `Person`, so it inherits its fields and methods. You can access embedded fields directly from the outer struct.

```go
package main
import "fmt"

type Person struct {
    name string
    age  int
}

type Employee struct {
    Person
    position string
}

func main() {
    emp := Employee{
        Person: Person{name: "Alice", age: 30},
        position: "Developer",
    }
    fmt.Println("Name:", emp.name)
    fmt.Println("Age:", emp.age)
    fmt.Println("Position:", emp.position)
}
```
