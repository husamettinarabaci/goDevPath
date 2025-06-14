## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: Boolean Types  
#### ✅ Answer 17: Creating and using boolean variables

In Go, boolean variables are declared using the `bool` type. You can assign `true` or `false` values and print them using `fmt.Println`.

```go
package main
import "fmt"

func main() {
    var isActive bool = true
    fmt.Println(isActive) // Output: true
    isActive = false
    fmt.Println(isActive) // Output: false
}
```
