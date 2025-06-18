## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Rune and Byte Types  
#### ✅ Answer 20: Using the `rune` and `byte` types

In Go, `byte` is an alias for `uint8` and is used to represent ASCII characters, while `rune` is an alias for `int32` and is used for Unicode code points. Here is an example:

```go
package main
import "fmt"

func main() {
    var b byte = 'A'
    var r rune = '✓'
    fmt.Printf("b: %c, type: %T\n", b, b)
    fmt.Printf("r: %c, type: %T\n", r, r)
}
```
