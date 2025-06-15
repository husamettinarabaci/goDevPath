## 📘 Section: Standard Library Essentials  
### 🔹 Category: Using the `strings` package  
#### ✅ Answer 182: Using the `strings` package

The `strings` package provides many useful functions for string manipulation in Go. Here are some common operations:

```go
package main
import (
    "fmt"
    "strings"
)

func main() {
    text := "Go is Awesome!"
    fmt.Println(strings.Contains(text, "Awesome")) // true
    fmt.Println(strings.ToUpper(text))              // "GO IS AWESOME!"
    fmt.Println(strings.ToLower(text))              // "go is awesome!"
    words := strings.Split(text, " ")
    fmt.Println(words) // [Go is Awesome!]
}
```

This program demonstrates checking for a substring, changing case, and splitting a string using the `strings` package.
