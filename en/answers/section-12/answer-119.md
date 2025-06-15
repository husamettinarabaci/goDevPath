## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interfaces and reflection  
#### ✅ Answer 119: Interfaces and reflection

The `reflect` package in Go allows you to inspect the type and value of interface variables at runtime. This is useful for dynamic type analysis and advanced programming techniques.

Below is an example:

```go
package main
import (
    "fmt"
    "reflect"
)

type Animal interface {
    Speak() string
}

type Dog struct {
    Name string
}

func (d Dog) Speak() string {
    return "Woof!"
}

func main() {
    var a Animal = Dog{Name: "Rex"}
    fmt.Println("Dynamic type:", reflect.TypeOf(a))
    fmt.Println("Dynamic value:", reflect.ValueOf(a))

    // Accessing underlying struct fields using reflection
    v := reflect.ValueOf(a)
    if v.Kind() == reflect.Struct {
        for i := 0; i < v.NumField(); i++ {
            fmt.Printf("Field %d: %v\n", i, v.Field(i))
        }
    } else if v.Kind() == reflect.Interface {
        elem := v.Elem()
        for i := 0; i < elem.NumField(); i++ {
            fmt.Printf("Field %d: %v\n", i, elem.Field(i))
        }
    }
}
```

This example shows how to use `reflect.TypeOf` and `reflect.ValueOf` to inspect the dynamic type and value of an interface, and how to access the underlying struct fields.
