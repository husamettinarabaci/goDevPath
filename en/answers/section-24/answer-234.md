## 📘 Section: Common Patterns and Idioms
### 🔹 Category: Factory pattern in Go
#### ✅ Answer 234: Factory pattern in Go

The factory pattern provides a way to create objects without specifying the exact type. In Go, this is often done with a function that returns an interface implemented by different types.

```go
package main
import "fmt"

type Animal interface {
    Speak() string
}

type Dog struct{}
func (d Dog) Speak() string { return "Woof!" }

type Cat struct{}
func (c Cat) Speak() string { return "Meow!" }

func AnimalFactory(kind string) Animal {
    switch kind {
    case "dog":
        return Dog{}
    case "cat":
        return Cat{}
    default:
        return nil
    }
}

func main() {
    animals := []string{"dog", "cat"}
    for _, kind := range animals {
        a := AnimalFactory(kind)
        if a != nil {
            fmt.Println(a.Speak())
        }
    }
}
```

This pattern allows you to create objects with different behaviors through a common interface.
