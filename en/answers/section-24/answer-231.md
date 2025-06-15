## 📘 Section: Common Patterns and Idioms
### 🔹 Category: Error handling idioms
#### ✅ Answer 231: Error handling idioms

In Go, the idiomatic way to handle errors is to return them as the last return value from functions and check them explicitly. Wrapping errors with context helps with debugging.

```go
package main
import (
    "errors"
    "fmt"
)

func doSomething(flag bool) error {
    if !flag {
        return errors.New("something went wrong")
    }
    return nil
}

func main() {
    err := doSomething(false)
    if err != nil {
        // Wrap error with context
        err = fmt.Errorf("doSomething failed: %w", err)
        fmt.Println(err)
    }
}
```

This pattern makes error handling explicit and traceable, which is a core Go idiom.
