## 📘 Section: Maps  
### 🔹 Category: Maps with Struct Values  
#### ✅ Answer 96: Maps with struct values

You can use structs as values in a Go map. This is useful for grouping related data. Here is an example:

```go
package main
import "fmt"

type Product struct {
    Price  float64
    Stock  int
}

func main() {
    products := map[string]Product{
        "apple":  {Price: 1.2, Stock: 10},
        "banana": {Price: 0.8, Stock: 20},
    }
    fmt.Println(products)
    for name, info := range products {
        fmt.Printf("%s: Price=%.2f, Stock=%d\n", name, info.Price, info.Stock)
    }
}
```

This program defines a struct, uses it as the value type in a map, and prints the map's contents.
