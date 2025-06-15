## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input  
#### ✅ Answer 32: Parsing user input to a number

You can use `fmt.Scanln` to read input as a string and `strconv.Atoi` to convert it to an integer. This example reads a number as text, parses it, and prints the result.

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    var input string
    fmt.Print("Enter a number: ")
    fmt.Scanln(&input)
    num, err := strconv.Atoi(input)
    if err != nil {
        fmt.Println("Invalid number!")
        return
    }
    fmt.Println("Parsed number:", num)
}
```
