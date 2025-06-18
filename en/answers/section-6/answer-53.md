## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, and Recursion  
#### ✅ Answer 53: Introduction to anonymous functions

Anonymous functions in Go are functions without a name. They can be defined and called immediately. Here is an example that prints a message using an anonymous function.

```go
package main
import "fmt"

func main() {
    func() {
        fmt.Println("Hello from an anonymous function!")
    }()
}
```
