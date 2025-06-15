## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 168: Creating and deleting directories

To create and delete directories in Go, use `os.Mkdir` to create a directory, `os.Create` to create a file, and `os.Remove`/`os.RemoveAll` to delete files and directories. Always handle errors and close files when done.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Create directory
    err := os.Mkdir("testdir", 0755)
    if err != nil {
        fmt.Println("Error creating directory:", err)
        return
    }

    // Create file inside directory
    file, err := os.Create("testdir/note.txt")
    if err != nil {
        fmt.Println("Error creating file:", err)
        return
    }
    _, err = file.WriteString("Test note")
    if err != nil {
        fmt.Println("Error writing to file:", err)
        file.Close()
        return
    }
    file.Close()

    // Delete file
    err = os.Remove("testdir/note.txt")
    if err != nil {
        fmt.Println("Error deleting file:", err)
        return
    }

    // Delete directory
    err = os.Remove("testdir")
    if err != nil {
        fmt.Println("Error deleting directory:", err)
        return
    }

    fmt.Println("Directory and file created and deleted successfully.")
}
```
