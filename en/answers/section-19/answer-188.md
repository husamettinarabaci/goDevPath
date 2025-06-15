## 📘 Section: Standard Library Essentials
### 🔹 Category: bufio Package
#### ✅ Answer 188: Using the `bufio` package

The `bufio` package provides buffered I/O, which is efficient for reading files line by line. `bufio.Scanner` is commonly used for this purpose.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("data.txt")
    if err != nil {
        fmt.Println("Error opening file:", err)
        return
    }
    defer file.Close()

    scanner := bufio.NewScanner(file)
    for scanner.Scan() {
        fmt.Println(scanner.Text())
    }

    if err := scanner.Err(); err != nil {
        fmt.Println("Error reading file:", err)
    }
}
```
