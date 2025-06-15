## 📘 Section: Maps  
### 🔹 Category: Maps with Slice Values  
#### ✅ Answer 97: Maps with slice values

You can use slices as values in a Go map. This is useful for associating multiple values with a single key. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string][]int{
        "evens": {2, 4, 6},
        "odds":  {1, 3, 5},
    }
    fmt.Println(m)
    for key, values := range m {
        fmt.Printf("%s: %v\n", key, values)
    }
}
```

This program creates a map with slice values and prints its contents.
