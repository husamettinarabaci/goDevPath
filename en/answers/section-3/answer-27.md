## 📘 Section: Control Flow  
### 🔹 Category: Loops and Flow Control  
#### ✅ Answer 27: Using labels with `break` and `continue`

Labels can be used with `break` and `continue` to control the flow of nested loops. In this example, the program breaks out of both loops when `i == 2` and `j == 3`, and continues the outer loop when `j == 1`.

```go
package main
import "fmt"

func main() {
outer:
    for i := 1; i <= 3; i++ {
        for j := 1; j <= 3; j++ {
            if i == 2 && j == 3 {
                break outer
            }
            if j == 1 {
                continue outer
            }
            fmt.Printf("i = %d, j = %d\n", i, j)
        }
    }
}
```
