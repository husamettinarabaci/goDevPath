## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Type Switches with Interfaces  
#### ✅ Answer 109: Type switches with interfaces

A type switch in Go allows you to determine the dynamic type of an interface value and handle each type differently. Here is an example with two structs implementing the same interface:

```go
package main
import "fmt"

type Animal interface {
    Speak() string
}

type Dog struct {}
func (d Dog) Speak() string { return "Woof!" }

type Cat struct {}
func (c Cat) Speak() string { return "Meow!" }

func identify(a Animal) {
    switch v := a.(type) {
    case Dog:
        fmt.Println("It's a Dog:", v.Speak())
    case Cat:
        fmt.Println("It's a Cat:", v.Speak())
    default:
        fmt.Println("Unknown animal")
    }
}

func main() {
    var a Animal
    a = Dog{}
    identify(a)
    a = Cat{}
    identify(a)
}
```
