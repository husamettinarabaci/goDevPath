## 📘 Section: Error Handling  
### 🔹 Category: error type, custom errors, panic/recover  
#### ✅ Answer 138: Error handling best practices

Some best practices for error handling in Go include:

- Always check and handle errors returned from functions.
- Return errors instead of panicking, except for truly exceptional situations.
- Provide clear and descriptive error messages.

Example:

```go
package main
import (
    "errors"
    "fmt"
)

func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("cannot divide by zero")
    }
    return a / b, nil
}

func main() {
    result, err := divide(10, 0)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    fmt.Println("Result:", result)
}
```
