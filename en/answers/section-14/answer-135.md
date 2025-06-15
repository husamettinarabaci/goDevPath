## 📘 Section: Error Handling  
### 🔹 Category: Wrapping Errors  
#### ✅ Answer 135: Wrapping errors

Go 1.13+ supports error wrapping using `fmt.Errorf` with the `%w` verb. You can inspect wrapped errors with `errors.Is` and `errors.Unwrap`.

```go
package main

import (
    "errors"
    "fmt"
)

var ErrNotFound = errors.New("not found")

func findItem(id int) error {
    if id != 1 {
        return ErrNotFound
    }
    return nil
}

func getItem(id int) error {
    if err := findItem(id); err != nil {
        return fmt.Errorf("getItem failed: %w", err)
    }
    return nil
}

func main() {
    err := getItem(2)
    if err != nil {
        fmt.Println("Error:", err)
        if errors.Is(err, ErrNotFound) {
            fmt.Println("Original error is ErrNotFound")
        }
    }
}
```

This example shows how to wrap and inspect errors in Go.
