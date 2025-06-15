## 📘 Section: Maps  
### 🔹 Category: Checking for Key Existence  
#### ✅ Answer 95: Checking for key existence

In Go, you can check if a key exists in a map using the "comma ok" idiom. Here is an example:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 3}
    if _, ok := m["apple"]; ok {
        fmt.Println("Key 'apple' exists in the map.")
    } else {
        fmt.Println("Key 'apple' does not exist in the map.")
    }
    if _, ok := m["orange"]; ok {
        fmt.Println("Key 'orange' exists in the map.")
    } else {
        fmt.Println("Key 'orange' does not exist in the map.")
    }
}
```

This program checks for the existence of keys and prints the result for each.
