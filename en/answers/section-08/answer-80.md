## 📘 Section: Structs  
### 🔹 Category: Structs and JSON Encoding/Decoding  
#### ✅ Answer 80: Structs and JSON encoding/decoding

Go's `encoding/json` package allows you to easily encode (marshal) structs to JSON and decode (unmarshal) JSON into structs.

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Product struct {
    Name  string  `json:"name"`
    Price float64 `json:"price"`
}

func main() {
    p := Product{Name: "Laptop", Price: 1299.99}
    // Encode to JSON
    data, err := json.Marshal(p)
    if err != nil {
        fmt.Println("Error marshaling:", err)
        return
    }
    fmt.Println(string(data))

    // Decode from JSON
    var decoded Product
    err = json.Unmarshal(data, &decoded)
    if err != nil {
        fmt.Println("Error unmarshaling:", err)
        return
    }
    fmt.Printf("Decoded: %+v\n", decoded)
}
```
