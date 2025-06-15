## 📘 Section: Standard Library Essentials  
### 🔹 Category: Using the `fmt` package  
#### ✅ Answer 181: Using the `fmt` package

The `fmt` package in Go provides functions for formatted I/O. `fmt.Printf` allows you to print values using format verbs such as `%s` for strings, `%d` for integers, and `%f` for floating-point numbers.

Example:

```go
package main
import "fmt"

func main() {
    name := "Go"
    age := 15
    pi := 3.14159
    fmt.Printf("Name: %s\n", name)         // string
    fmt.Printf("Age: %d\n", age)           // integer
    fmt.Printf("Pi: %f\n", pi)             // float (default 6 decimals)
    fmt.Printf("Pi (2 decimals): %.2f\n", pi) // float with 2 decimals
}
```

This program demonstrates formatted output for different types using the `fmt` package.
