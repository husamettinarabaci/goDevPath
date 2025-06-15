## 📘 Section: I/O Basics  
### 🔹 Category: Terminal Input  
#### ✅ Answer 31: Reading input from the terminal with `fmt.Scanln`

You can use `fmt.Scanln` to read a line of input from the terminal. This example prompts the user, reads their input, and prints it back.

```go
package main
import "fmt"

func main() {
    var input string
    fmt.Print("Enter some text: ")
    fmt.Scanln(&input)
    fmt.Println("You entered:", input)
}
```
