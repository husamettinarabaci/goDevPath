## 📘 Section: Error Handling  
### 🔹 Category: error type, custom errors, panic/recover  
#### ✅ Answer 139: Error handling in main

In Go, it is common to handle errors in the `main` function by checking the error returned from other functions and printing a user-friendly message. This helps prevent the program from crashing unexpectedly.

```go
package main
import (
    "errors"
    "fmt"
)

func doSomething() error {
    return errors.New("something went wrong")
}

func main() {
    err := doSomething()
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    fmt.Println("Operation successful")
}
```
