## 📘 Section: Structs  
### 🔹 Category: Anonymous Structs  
#### ✅ Answer 75: Anonymous structs

Anonymous structs in Go are useful for quick, one-off data structures without a named type. You can declare, initialize, and use them directly.

```go
package main
import "fmt"

func main() {
    book := struct {
        title string
        pages int
    }{
        title: "Go Programming",
        pages: 350,
    }
    fmt.Println("Title:", book.title)
    fmt.Println("Pages:", book.pages)
}
```
