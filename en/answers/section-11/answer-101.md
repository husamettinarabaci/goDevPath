## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Methods  
#### ✅ Answer 101: Defining methods on structs

In Go, you can define methods on struct types. A method is a function with a receiver argument. Here is an example:

```go
package main
import "fmt"

type Person struct {
    Name string
}

func (p Person) Greet() {
    fmt.Println("Hello, my name is", p.Name)
}

func main() {
    person := Person{Name: "Alice"}
    person.Greet()
}
```
