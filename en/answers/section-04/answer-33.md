## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input and Error Handling  
#### ✅ Answer 33: Handling input errors gracefully

This program reads input from the user, tries to convert it to an integer using `strconv.Atoi`, and checks for errors. If the input is not a valid integer, it prints a clear error message instead of crashing.

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    var input string
    fmt.Print("Enter a number: ")
    _, err := fmt.Scanln(&input)
    if err != nil {
        fmt.Println("Error reading input:", err)
        return
    }
    num, err := strconv.Atoi(input)
    if err != nil {
        fmt.Println("Invalid number. Please enter a valid integer.")
        return
    }
    fmt.Println("You entered:", num)
}
```
