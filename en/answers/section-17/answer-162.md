## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 162: Writing to a file

To write to a file in Go, use `os.Create` to create or truncate the file, and `WriteString` or `ioutil.WriteFile` to write data. Always handle errors and close the file when done.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.Create("output.txt")
    if err != nil {
        fmt.Println("Error creating file:", err)
        return
    }
    defer file.Close()

    _, err = file.WriteString("Hello, Go file!")
    if err != nil {
        fmt.Println("Error writing to file:", err)
        return
    }

    fmt.Println("File written successfully.")
}
```
