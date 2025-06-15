## 📘 Section: Advanced Go Features  
### 🔹 Category: Reflection  
#### ✅ Answer 201: Using reflection with `reflect` package

The `reflect` package in Go allows you to inspect types and values at runtime. Here, we define a struct and use reflection to print its field names and types.

```go
package main
import (
    "fmt"
    "reflect"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{"Alice", 30}
    t := reflect.TypeOf(p)
    v := reflect.ValueOf(p)
    fmt.Println("Type:", t.Name())
    for i := 0; i < t.NumField(); i++ {
        field := t.Field(i)
        value := v.Field(i)
        fmt.Printf("Field: %s\tType: %s\tValue: %v\n", field.Name, field.Type, value)
    }
}
```
