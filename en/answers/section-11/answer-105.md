## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Interfaces  
#### ✅ Answer 105: Defining a simple interface

In Go, an interface is a type that specifies a set of method signatures. Any type that implements those methods satisfies the interface. Example:

```go
package main
import "fmt"

type Greeter interface {
    Greet()
}

type Person struct {
    Name string
}

func (p Person) Greet() {
    fmt.Println("Hello, my name is", p.Name)
}

func SayHello(g Greeter) {
    g.Greet()
}

func main() {
    p := Person{Name: "Alice"}
    SayHello(p)
}
```
