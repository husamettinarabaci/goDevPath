## 📘 Section: Maps  
### 🔹 Category: Adding and Removing Map Entries  
#### ✅ Answer 92: Adding and removing map entries

You can add entries to a Go map by assigning a value to a new key, and remove entries using the `delete` function. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"apple": 5}
    fmt.Println("Initial map:", m)
    m["banana"] = 3
    fmt.Println("After adding banana:", m)
    delete(m, "apple")
    fmt.Println("After deleting apple:", m)
}
```

This program shows how to add and remove entries in a map and prints the map after each operation.
