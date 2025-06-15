## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and Number Parsing  
#### ✅ Answer 38: Reading and parsing a float

This program prompts the user for a floating-point number, reads the input, parses it into a `float64` using `strconv.ParseFloat`, and handles errors gracefully.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
    "strconv"
    "strings"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Enter a floating-point number: ")
    input, _ := reader.ReadString('\n')
    input = strings.TrimSpace(input)
    num, err := strconv.ParseFloat(input, 64)
    if err != nil {
        fmt.Println("Invalid input. Please enter a valid floating-point number.")
        return
    }
    fmt.Println("You entered:", num)
}
```
