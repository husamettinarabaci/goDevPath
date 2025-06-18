## 📘 Section: Structs  
### 🔹 Category: Structs and Zero Values  
#### ✅ Answer 78: Structs and zero values

In Go, struct fields are automatically assigned zero values if not explicitly initialized. For example, strings default to `""` and integers to `0`.

```go
package main
import "fmt"

type User struct {
    name string
    age  int
}

func main() {
    var u User
    fmt.Println("Name:", u.name) // empty string
    fmt.Println("Age:", u.age)   // 0
}
```
