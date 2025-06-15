## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and Character Handling  
#### ✅ Answer 35: Reading a single character from input

This program prompts the user for a single character, reads it using `bufio.Reader` and `ReadRune`, and prints the character. Note: On most systems, the user will need to press Enter after typing the character.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Enter a single character: ")
    char, _, err := reader.ReadRune()
    if err != nil {
        fmt.Println("Error reading character:", err)
        return
    }
    fmt.Printf("You entered: %c\n", char)
}
```
