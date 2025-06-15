## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interfaces and JSON encoding/decoding  
#### ✅ Answer 115: Interfaces and JSON encoding/decoding

Encoding and decoding interface values with JSON in Go requires special handling because type information is lost during marshaling. One common approach is to use a custom type field to preserve type information.

Below is an example demonstrating how to encode and decode a slice of interface values:

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Animal interface {
    Speak() string
}

type Dog struct {
    Type  string `json:"type"`
    Name  string `json:"name"`
    Breed string `json:"breed"`
}

func (d Dog) Speak() string {
    return "Woof!"
}

type Cat struct {
    Type string `json:"type"`
    Name string `json:"name"`
    Color string `json:"color"`
}

func (c Cat) Speak() string {
    return "Meow!"
}

func main() {
    animals := []Animal{
        Dog{Type: "dog", Name: "Rex", Breed: "Labrador"},
        Cat{Type: "cat", Name: "Whiskers", Color: "Tabby"},
    }

    // Marshal: convert to []interface{} for JSON encoding
    var raw []interface{}
    for _, a := range animals {
        raw = append(raw, a)
    }
    data, _ := json.Marshal(raw)
    fmt.Println(string(data))

    // Unmarshal: decode and use type field to reconstruct
    var decoded []map[string]interface{}
    _ = json.Unmarshal(data, &decoded)
    for _, item := range decoded {
        switch item["type"] {
        case "dog":
            dog := Dog{
                Type:  item["type"].(string),
                Name:  item["name"].(string),
                Breed: item["breed"].(string),
            }
            fmt.Println(dog.Name, "says", dog.Speak())
        case "cat":
            cat := Cat{
                Type:  item["type"].(string),
                Name:  item["name"].(string),
                Color: item["color"].(string),
            }
            fmt.Println(cat.Name, "says", cat.Speak())
        }
    }
}
```

This example uses a `type` field to distinguish between struct types when decoding. This way, you can correctly reconstruct the original types from the JSON data.
