## 📘 Section: Structs  
### 🔹 Category: Structs with Pointer Fields  
#### ✅ Answer 76: Structs with pointer fields

Structs in Go can have fields that are pointers, allowing you to reference data stored elsewhere. This is useful for sharing or updating data without copying it.

```go
package main
import "fmt"

type Book struct {
    title  string
    author *string
}

func main() {
    authorName := "John Doe"
    b := Book{
        title:  "Go in Action",
        author: &authorName,
    }
    fmt.Println("Title:", b.title)
    fmt.Println("Author:", *b.author)
}
```
