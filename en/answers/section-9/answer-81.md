## 📘 Section: Arrays and Slices  
### 🔹 Category: Declaring and Initializing Arrays  
#### ✅ Answer 81: Declaring and initializing arrays

In Go, arrays have a fixed length and can be declared and initialized in a single line.

```go
package main
import "fmt"

func main() {
    var arr [5]int = [5]int{1, 2, 3, 4, 5}
    fmt.Println(arr)
}
```
