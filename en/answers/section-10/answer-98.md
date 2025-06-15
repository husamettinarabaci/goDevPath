## 📘 Section: Maps  
### 🔹 Category: Map Operations  
#### ✅ Answer 98: Deleting map entries

To delete an entry from a map in Go, use the built-in `delete` function. This function takes the map and the key to remove. If the key does not exist, `delete` does nothing. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"a": 1, "b": 2, "c": 3}
    fmt.Println("Before deletion:", m)
    delete(m, "b")
    fmt.Println("After deleting 'b':", m)
    delete(m, "x") // Deleting a non-existent key is safe
    fmt.Println("After attempting to delete 'x':", m)
}
```
