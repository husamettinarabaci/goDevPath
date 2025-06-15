## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and EOF Handling  
#### ✅ Answer 36: Reading input until EOF

This program reads lines from the terminal until EOF is reached, stores them in a slice, and prints all lines at the end. It uses `bufio.Scanner` for line-by-line input and checks for EOF automatically.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    var lines []string
    scanner := bufio.NewScanner(os.Stdin)
    fmt.Println("Enter lines (Ctrl+D to end):")
    for scanner.Scan() {
        lines = append(lines, scanner.Text())
    }
    if err := scanner.Err(); err != nil {
        fmt.Println("Error reading input:", err)
        return
    }
    fmt.Println("\nAll lines entered:")
    for _, line := range lines {
        fmt.Println(line)
    }
}
```
