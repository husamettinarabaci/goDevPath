## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interfaces and Slices  
#### ✅ Answer 113: Interfaces and slices

A slice of interface type in Go can hold values of any type that implements the interface. This allows you to store and use different concrete types in a single collection. Here is an example:

```go
package main
import "fmt"

type Speaker interface {
    Speak() string
}

type Dog struct {}
func (d Dog) Speak() string { return "Woof!" }

type Cat struct {}
func (c Cat) Speak() string { return "Meow!" }

func main() {
    var animals []Speaker
    animals = append(animals, Dog{}, Cat{})
    for _, a := range animals {
        fmt.Println(a.Speak())
    }
}
```
