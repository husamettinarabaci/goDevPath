## 📘 Section: Error Handling  
### 🔹 Category: Returning Errors  
#### ✅ Answer 131: Returning errors from functions

In Go, it's common to return an error as the last return value from a function. You can use the built-in `error` type and the `errors.New` function to create errors.

```go
package main

import (
    "errors"
    "fmt"
)

func checkPositive(n int) error {
    if n < 0 {
        return errors.New("value must be non-negative")
    }
    return nil
}

func main() {
    if err := checkPositive(5); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Value is valid.")
    }

    if err := checkPositive(-2); err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Value is valid.")
    }
}
```

This pattern allows you to handle errors gracefully in Go programs.
