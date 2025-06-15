## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and Slices  
#### ✅ Answer 39: Reading input into a slice

This program prompts the user for space-separated values, reads the input, splits it into a slice using `strings.Fields`, and prints the resulting slice.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Enter values separated by spaces: ")
    input, _ := reader.ReadString('\n')
    input = strings.TrimSpace(input)
    values := strings.Fields(input)
    fmt.Println("Slice:", values)
}
```
