## 📘 Section: Standard Library Essentials  
### 🔹 Category: Using the `strconv` package  
#### ✅ Answer 183: Using the `strconv` package

The `strconv` package provides functions for converting between strings and numbers in Go.

Example:

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    // String to int
    s := "42"
    i, err := strconv.Atoi(s)
    if err != nil {
        fmt.Println("Conversion error:", err)
    } else {
        fmt.Println("String to int:", i)
    }

    // Int to string
    n := 123
    str := strconv.Itoa(n)
    fmt.Println("Int to string:", str)

    // Float to string with precision
    f := 3.14159
    fstr := strconv.FormatFloat(f, 'f', 2, 64)
    fmt.Println("Float to string (2 decimals):", fstr)
}
```

This program demonstrates converting between strings and numbers using the `strconv` package.
