## 📘 Section: Structs and Methods  
### 🔹 Category: Structs and JSON  
#### ✅ Answer 259: Using structs with JSON marshaling

Go's `encoding/json` package can marshal structs to JSON. Here, a `Product` struct is marshaled and printed as a JSON string.

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Product struct {
    ID   int    `json:"id"`
    Name string `json:"name"`
}

func main() {
    p := Product{ID: 101, Name: "Book"}
    data, _ := json.Marshal(p)
    fmt.Println(string(data))
}
```
