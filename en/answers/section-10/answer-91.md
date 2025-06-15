## 📘 Section: Maps  
### 🔹 Category: Declaring and Initializing Maps  
#### ✅ Answer 91: Declaring and initializing maps

In Go, maps are reference types that associate keys with values. You can declare a map using the `map` keyword and initialize it with a composite literal or with the `make` function. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 3}
    fmt.Println(m)
}
```

This creates a map with string keys and int values, initializes it with two pairs, and prints the map.
