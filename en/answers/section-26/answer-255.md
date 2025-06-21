## 📘 Section: Structs and Methods  
### 🔹 Category: Interfaces and Structs  
#### ✅ Answer 255: Using interface methods with structs

Interfaces allow different types to implement common behavior. Here, `Robot` implements the `Speaker` interface, and a function uses the interface type.

```go
package main
import "fmt"

type Speaker interface {
    Speak() string
}

type Robot struct{}

func (r Robot) Speak() string {
    return "Beep boop!"
}

func announce(s Speaker) {
    fmt.Println(s.Speak())
}

func main() {
    rob := Robot{}
    announce(rob)
}
```
