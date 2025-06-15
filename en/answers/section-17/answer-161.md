## 📘 Section: File and Directory Operations  
### 🔹 Category: Reading Files  
#### ✅ Answer 161: Reading a file

To read a file in Go, you can use the `os` and `io/ioutil` (or `os` and `io`) packages. This example reads the contents of `example.txt` and prints it to the terminal. Error handling ensures the program does not crash if the file is missing or unreadable.

```go
package main
import (
    "fmt"
    "io/ioutil"
    "os"
)

func main() {
    data, err := ioutil.ReadFile("example.txt")
    if err != nil {
        fmt.Println("Error reading file:", err)
        return
    }
    fmt.Print(string(data))
}
```
