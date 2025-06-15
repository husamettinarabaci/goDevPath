## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and User Prompts  
#### ✅ Answer 37: Reading input with a prompt

This program displays a prompt, reads a line of input from the user, and prints the input. It uses `bufio.Reader` for flexible input handling.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Please enter your name: ")
    input, _ := reader.ReadString('\n')
    fmt.Printf("You entered: %s", input)
}
```
