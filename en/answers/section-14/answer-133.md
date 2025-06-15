## 📘 Section: Error Handling  
### 🔹 Category: Creating Custom Error Types  
#### ✅ Answer 133: Creating custom error types

You can create custom error types in Go by defining a struct and implementing the `Error()` method. This allows you to add extra context to errors.

```go
package main

import "fmt"

type NegativeError struct {
    Value int
}

func (e *NegativeError) Error() string {
    return fmt.Sprintf("negative value: %d", e.Value)
}

func checkPositive(n int) error {
    if n < 0 {
        return &NegativeError{Value: n}
    }
    return nil
}

func main() {
    if err := checkPositive(-5); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Value is valid.")
    }
}
```

This pattern is useful for providing detailed error information.
