## 📘 Section: Control Flow  
### 🔹 Category: Goto Statement  
#### ✅ Answer 30: Using `goto` in Go

The `goto` statement allows you to jump to a labeled statement in your code. In this example, the loop prints numbers from 1 to 5, but when the number is 3, it jumps to the label after the loop and prints a message.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 5; i++ {
        if i == 3 {
            goto end
        }
        fmt.Println(i)
    }
end:
    fmt.Println("Jumped to the end label!")
}
```
