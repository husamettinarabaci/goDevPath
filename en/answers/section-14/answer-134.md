## 📘 Section: Error Handling  
### 🔹 Category: Using errors.New and fmt.Errorf  
#### ✅ Answer 134: Using `errors.New` and `fmt.Errorf`

You can use `errors.New` to create a simple error and `fmt.Errorf` to create formatted error messages in Go.

```go
package main

import (
    "errors"
    "fmt"
)

func validateAge(age int) error {
    if age < 0 {
        return errors.New("age cannot be negative")
    }
    if age > 120 {
        return fmt.Errorf("age %d is unrealistically high", age)
    }
    return nil
}

func main() {
    if err := validateAge(-1); err != nil {
        fmt.Println("Error:", err)
    }
    if err := validateAge(150); err != nil {
        fmt.Println("Error:", err)
    }
    if err := validateAge(30); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Age is valid.")
    }
}
```

This example shows how to use both error creation methods for different situations.
