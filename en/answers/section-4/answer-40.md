## 📘 Section: I/O Basics  
### 🔹 Category: File Input  
#### ✅ Answer 40: Reading input from a file

This program opens a file (e.g., `input.txt`), reads its contents line by line using `bufio.Scanner`, and prints each line. It handles errors if the file cannot be opened or read.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("input.txt")
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
