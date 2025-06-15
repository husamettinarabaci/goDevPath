## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interfaces and dynamic types  
#### ✅ Answer 120: Interfaces and dynamic types

A type switch in Go allows you to determine the dynamic type of an interface value at runtime and handle each type differently.

Below is an example:

```go
package main
import "fmt"

type Animal interface {
    Speak() string
}

type Dog struct {
    Name string
}

func (d Dog) Speak() string {
    return "Woof!"
}

type Cat struct {
    Name string
}

func (c Cat) Speak() string {
    return "Meow!"
}

func describe(a Animal) {
    switch v := a.(type) {
    case Dog:
        fmt.Println("It's a Dog named", v.Name)
    case Cat:
        fmt.Println("It's a Cat named", v.Name)
    default:
        fmt.Println("Unknown animal")
    }
}

func main() {
    describe(Dog{Name: "Rex"})
    describe(Cat{Name: "Whiskers"})
}
```

This example shows how to use a type switch to handle different dynamic types stored in an interface.
