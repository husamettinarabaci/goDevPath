## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Resource cleanup with `defer`  
#### ✅ Answer 237: Resource cleanup with `defer`

The `defer` statement in Go is commonly used to ensure that resources are released, even if a function returns early or an error occurs. This is especially important for files, network connections, and other resources that must be closed.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("example.txt")
    if err != nil {
        fmt.Println("Error opening file:", err)
        return
    }
    defer file.Close() // Ensures the file is closed when main returns

    // Perform file operations here
    fmt.Println("File opened successfully.")
}
```

If you forget to use `defer file.Close()`, the file may remain open, potentially causing resource leaks. Using `defer` guarantees cleanup regardless of how the function exits.
