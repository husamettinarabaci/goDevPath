## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 169: Walking a directory tree

This program demonstrates how to recursively walk through a directory tree in Go. The `filepath.Walk` function is used to visit every file and directory starting from the current directory. Each path is printed, and errors are handled appropriately.

```go
package main
import (
    "fmt"
    "os"
    "path/filepath"
)

func main() {
    err := filepath.Walk(".", func(path string, info os.FileInfo, err error) error {
        if err != nil {
            fmt.Println("Error:", err)
            return err
        }
        fmt.Println(path)
        return nil
    })
    if err != nil {
        fmt.Println("Walk error:", err)
    }
}
```
