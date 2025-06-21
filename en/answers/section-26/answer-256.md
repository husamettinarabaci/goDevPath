## 📘 Section: Structs and Methods  
### 🔹 Category: Struct Tags and Reflection  
#### ✅ Answer 256: Struct tags and reflection use

Struct tags provide metadata for fields. Here, we use JSON tags and reflection to access them.

```go
package main
import (
    "encoding/json"
    "fmt"
    "reflect"
)

type User struct {
    ID    int    `json:"id"`
    Email string `json:"email"`
}

func main() {
    u := User{ID: 1, Email: "user@example.com"}
    data, _ := json.Marshal(u)
    fmt.Println(string(data))

    t := reflect.TypeOf(u)
    for i := 0; i < t.NumField(); i++ {
        field := t.Field(i)
        fmt.Printf("Field: %s, Tag: %s\n", field.Name, field.Tag)
    }
}
```
