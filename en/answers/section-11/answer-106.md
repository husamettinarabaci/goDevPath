## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Methods and Interfaces  
#### ✅ Answer 106: Implementing an interface

To implement an interface in Go, define the interface type and then create a struct with methods that match the interface's method signatures. Any type that implements all the methods of an interface is said to satisfy that interface.

```go
package main
import "fmt"

// Define the interface
type Greeter interface {
    Greet() string
}

// Create a struct that implements the interface
type Person struct {
    Name string
}

// Implement the Greet method
func (p Person) Greet() string {
    return "Hello, " + p.Name
}

func main() {
    var g Greeter = Person{Name: "Go Developer"}
    fmt.Println(g.Greet())
}
```
