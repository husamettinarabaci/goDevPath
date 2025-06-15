## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 163: Appending to a file

To append to a file in Go, use `os.OpenFile` with the `os.O_APPEND|os.O_CREATE|os.O_WRONLY` flags. This allows you to open the file for appending, create it if it doesn't exist, and write to it. Always handle errors and close the file when done.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.OpenFile("log.txt", os.O_APPEND|os.O_CREATE|os.O_WRONLY, 0644)
    if err != nil {
        fmt.Println("Error opening file:", err)
        return
    }
    defer file.Close()

    _, err = file.WriteString("New log entry\n")
    if err != nil {
        fmt.Println("Error appending to file:", err)
        return
    }

    fmt.Println("Log entry appended.")
}
```
