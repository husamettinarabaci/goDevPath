## 📘 Section: Control Flow  
### 🔹 Category: Loops and Flow Control  
#### ✅ Answer 26: Skipping a loop iteration with `continue`

The `continue` statement is used to skip the current iteration of a loop and move to the next one. In this example, the loop prints numbers from 1 to 10, but skips printing the number 5.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 10; i++ {
        if i == 5 {
            continue
        }
        fmt.Println(i)
    }
}
```
