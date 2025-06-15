## 📘 Section: Maps  
### 🔹 Category: Maps  
#### ✅ Answer 99: Maps and zero values

In Go, the zero value of a map is `nil`. A nil map has no keys, cannot store values, and behaves differently from an initialized (but empty) map. You can check if a map is nil using a simple comparison. Example:

```go
package main
import "fmt"

func main() {
    var m map[string]int // zero value is nil
    if m == nil {
        fmt.Println("The map is nil.")
    } else {
        fmt.Println("The map is not nil.")
    }
}
```
