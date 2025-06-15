## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Type Assertions with Interfaces  
#### ✅ Answer 108: Type assertions with interfaces

Type assertions in Go allow you to retrieve the concrete value stored in an interface variable. You can use the `value, ok := iface.(Type)` syntax to safely check and extract the underlying type. Here is an example:

```go
package main
import "fmt"

type Describer interface {
    Describe() string
}

type Person struct {
    Name string
}

func (p Person) Describe() string {
    return "Person: " + p.Name
}

func main() {
    var d Describer = Person{Name: "Go Dev"}
    fmt.Println(d.Describe())

    // Type assertion
    p, ok := d.(Person)
    if ok {
        fmt.Println("Type assertion successful! Name:", p.Name)
    } else {
        fmt.Println("Type assertion failed.")
    }
}
```
