## 📘 Section: Maps  
### 🔹 Category: Accessing Map Values Safely  
#### ✅ Answer 93: Accessing map values safely

In Go, you can safely access map values using the "comma ok" idiom, which tells you whether a key exists in the map. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 3}
    value, ok := m["apple"]
    if ok {
        fmt.Println("apple exists with value:", value)
    } else {
        fmt.Println("apple does not exist")
    }
    value, ok = m["orange"]
    if ok {
        fmt.Println("orange exists with value:", value)
    } else {
        fmt.Println("orange does not exist")
    }
}
```

This program demonstrates how to check for the existence of a key before using its value.
