## 📘 Section: Control Flow  
### 🔹 Category: Loops and Flow Control  
#### ✅ Answer 25: Breaking out of a loop with `break`

The `break` statement is used to exit a loop before it finishes all its iterations. In this example, the loop prints numbers from 1 to 10, but stops when the number reaches 5.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 10; i++ {
        fmt.Println(i)
        if i == 5 {
            break
        }
    }
}
```
