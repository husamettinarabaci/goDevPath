## 📘 Section: Error Handling  
### 🔹 Category: Using the error Type  
#### ✅ Answer 132: Using the `error` type

The built-in `error` type in Go is used to represent error conditions. You can return an error from a function and check it in the caller.

```go
package main

import (
    "errors"
    "fmt"
)

func checkNotEmpty(s string) error {
    if s == "" {
        return errors.New("string must not be empty")
    }
    return nil
}

func main() {
    if err := checkNotEmpty(""); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("String is valid.")
    }

    if err := checkNotEmpty("Go"); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("String is valid.")
    }
}
```

This demonstrates how to use the `error` type for error handling in Go.
