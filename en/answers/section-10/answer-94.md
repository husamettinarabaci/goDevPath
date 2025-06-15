## 📘 Section: Maps  
### 🔹 Category: Iterating Over a Map  
#### ✅ Answer 94: Iterating over a map

You can iterate over a map in Go using a `for` loop with the `range` keyword. This allows you to access each key and value in the map. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 3}
    for key, value := range m {
        fmt.Printf("Key: %s, Value: %d\n", key, value)
    }
}
```

This program prints each key and value in the map using a `for` loop with `range`.
