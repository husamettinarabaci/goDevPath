## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and String Processing  
#### ✅ Answer 34: Trimming whitespace from input

This program reads a line of input from the user, trims any leading and trailing whitespace using the `strings.TrimSpace` function, and prints the cleaned string. This is useful for sanitizing user input in Go.

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
    fmt.Print("Enter some text: ")
    input, _ := reader.ReadString('\n')
    cleaned := strings.TrimSpace(input)
    fmt.Println("Trimmed input:", cleaned)
}
```
