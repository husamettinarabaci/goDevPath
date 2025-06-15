## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 167: Creating and deleting files

To create and delete files in Go, use `os.Create` to create and write to a file, and `os.Remove` to delete it. Always handle errors and close files when done.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Create and write to file
    file, err := os.Create("temp.txt")
    if err != nil {
        fmt.Println("Error creating file:", err)
        return
    }
    _, err = file.WriteString("Temporary file")
    if err != nil {
        fmt.Println("Error writing to file:", err)
        file.Close()
        return
    }
    file.Close()

    // Delete the file
    err = os.Remove("temp.txt")
    if err != nil {
        fmt.Println("Error deleting file:", err)
        return
    }

    fmt.Println("File created and deleted successfully.")
}
```
