## 📘 Section: Structs  
### 🔹 Category: Accessing struct fields  
#### ✅ Answer 72: Accessing struct fields

You can access struct fields in Go using the dot (`.`) notation. Here, we define a `Book` struct, create an instance, and print each field separately.

```go
package main
import "fmt"

type Book struct {
    title string
    pages int
}

func main() {
    b := Book{"Go in Action", 300}
    fmt.Println(b.title)
    fmt.Println(b.pages)
}
```
