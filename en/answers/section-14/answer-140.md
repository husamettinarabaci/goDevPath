## 📘 Section: Error Handling  
### 🔹 Category: error type, custom errors, panic/recover  
#### ✅ Answer 140: Error handling in libraries

In Go libraries, functions should return errors to the caller instead of handling them internally. The user of the library is responsible for checking and handling the error.

Example:

```go
// mylib/mylib.go
package mylib
import "errors"

func DoTask(input int) error {
    if input < 0 {
        return errors.New("input cannot be negative")
    }
    return nil
}
```

```go
// main.go
package main
import (
    "fmt"
    "mylib"
)

func main() {
    err := mylib.DoTask(-1)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    fmt.Println("Task completed successfully")
}
```
