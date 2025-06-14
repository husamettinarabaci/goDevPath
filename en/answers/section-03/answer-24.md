## 📘 Section: Control Flow  
### 🔹 Category: For Loops  
#### ✅ Answer 24: Using `for` as a while loop

In Go, the `for` loop can be used as a while loop by omitting the initialization and post statements. Here is an example:

```go
package main
import "fmt"

func main() {
    i := 1
    for i <= 5 {
        fmt.Println(i)
        i++
    }
}
```
