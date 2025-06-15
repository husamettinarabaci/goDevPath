## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 170: File permissions and modes

This program demonstrates how to create a file with specific permissions, change its permissions, and display them in Go. The `os.OpenFile` function is used to create the file, `os.Chmod` changes the permissions, and `os.Stat` retrieves the file info to print the permissions before and after the change.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    filename := "testfile.txt"
    // Create file with owner read/write only (0600)
    file, err := os.OpenFile(filename, os.O_CREATE|os.O_WRONLY, 0600)
    if err != nil {
        fmt.Println("Error creating file:", err)
        return
    }
    file.Close()

    info, err := os.Stat(filename)
    if err != nil {
        fmt.Println("Error stating file:", err)
        return
    }
    fmt.Printf("Permissions before: %v\n", info.Mode().Perm())

    // Change permissions to read/write for everyone (0666)
    err = os.Chmod(filename, 0666)
    if err != nil {
        fmt.Println("Error changing permissions:", err)
        return
    }

    info, err = os.Stat(filename)
    if err != nil {
        fmt.Println("Error stating file:", err)
        return
    }
    fmt.Printf("Permissions after: %v\n", info.Mode().Perm())
}
```
