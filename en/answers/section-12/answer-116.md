## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Custom error types with interfaces  
#### ✅ Answer 116: Custom error types with interfaces

In Go, you can define your own error types by implementing the `Error()` method from the `error` interface. This allows you to add custom fields and logic to your errors.

Below is an example of a custom error type and its usage:

```go
package main
import (
    "fmt"
)

type MyError struct {
    Code    int
    Message string
}

func (e MyError) Error() string {
    return fmt.Sprintf("Error %d: %s", e.Code, e.Message)
}

func riskyOperation(fail bool) error {
    if fail {
        return MyError{Code: 404, Message: "Resource not found"}
    }
    return nil
}

func main() {
    err := riskyOperation(true)
    if err != nil {
        // Type assertion to check for custom error
        if myErr, ok := err.(MyError); ok {
            fmt.Println("Custom error occurred:", myErr)
            fmt.Println("Error code:", myErr.Code)
        } else {
            fmt.Println("Other error:", err)
        }
    } else {
        fmt.Println("Operation succeeded.")
    }
}
```

This example shows how to define a custom error type, return it from a function, and use type assertion to access its fields when handling the error.
