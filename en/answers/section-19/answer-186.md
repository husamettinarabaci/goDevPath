## 📘 Section: Standard Library Essentials
### 🔹 Category: os Package
#### ✅ Answer 186: Using the `os` package

The `os` package provides functions for interacting with the operating system. Here, we use `os.Getwd` for the current directory, `os.Environ` for environment variables, and `os.Stat` to check file existence.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    // Print current working directory
    cwd, err := os.Getwd()
    if err != nil {
        fmt.Println("Error getting working directory:", err)
    } else {
        fmt.Println("Current working directory:", cwd)
    }

    // List all environment variables
    fmt.Println("Environment variables:")
    for _, env := range os.Environ() {
        fmt.Println(env)
    }

    // Check if test.txt exists
    if _, err := os.Stat("test.txt"); err == nil {
        fmt.Println("test.txt exists.")
    } else if os.IsNotExist(err) {
        fmt.Println("test.txt does not exist.")
    } else {
        fmt.Println("Error checking test.txt:", err)
    }
}
```
