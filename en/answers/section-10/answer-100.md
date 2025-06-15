## 📘 Section: Maps  
### 🔹 Category: Maps  
#### ✅ Answer 100: Maps and JSON encoding/decoding

You can use the `encoding/json` package to encode a map to JSON and decode JSON back into a map. Here is an example:

```go
package main
import (
    "encoding/json"
    "fmt"
)

func main() {
    m := map[string]int{"a": 1, "b": 2}
    // Encode to JSON
    jsonData, err := json.Marshal(m)
    if err != nil {
        fmt.Println("Error marshaling:", err)
        return
    }
    fmt.Println("JSON:", string(jsonData))

    // Decode back to map
    var m2 map[string]int
    err = json.Unmarshal(jsonData, &m2)
    if err != nil {
        fmt.Println("Error unmarshaling:", err)
        return
    }
    fmt.Println("Decoded map:", m2)
}
```
