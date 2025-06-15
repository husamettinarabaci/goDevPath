## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Empty Interface Usage  
#### ✅ Answer 112: Empty interface (`interface{}`) usage

The empty interface (`interface{}`) in Go can hold values of any type, making it useful for generic programming. You can use type assertions or the `fmt` package to inspect the value and its type at runtime. Here is an example:

```go
package main
import (
    "fmt"
    "reflect"
)

func printValue(v interface{}) {
    fmt.Printf("Value: %v, Type: %s\n", v, reflect.TypeOf(v))
}

func main() {
    var any interface{}
    any = 42
    printValue(any)
    any = "hello"
    printValue(any)
    any = struct{ Name string }{"Go"}
    printValue(any)
}
```
