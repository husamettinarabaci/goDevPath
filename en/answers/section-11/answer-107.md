## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Interface Usage  
#### ✅ Answer 107: Using interface values

Interface values in Go can hold any value that implements the interface. This allows you to write flexible code that works with different types. Here, two structs implement the same interface, and a function accepts the interface type, demonstrating polymorphism.

```go
package main
import "fmt"

// Define the interface
type Speaker interface {
    Speak() string
}

// First struct implementing the interface
type Dog struct {}
func (d Dog) Speak() string {
    return "Woof!"
}

// Second struct implementing the interface
type Cat struct {}
func (c Cat) Speak() string {
    return "Meow!"
}

// Function that accepts the interface
def makeSpeak(s Speaker) {
    fmt.Println(s.Speak())
}

func main() {
    var s Speaker
    s = Dog{}
    makeSpeak(s)
    s = Cat{}
    makeSpeak(s)
}
```
