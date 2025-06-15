## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Nil Interfaces and Zero Values  
#### ✅ Answer 110: Nil interfaces and zero values

In Go, the zero value of an interface is `nil`. This means an interface variable that has not been assigned any value is `nil`. You can check for this using a simple comparison. Here is an example:

```go
package main
import "fmt"

type Describer interface {
    Describe() string
}

func checkNil(i Describer) {
    if i == nil {
        fmt.Println("Interface is nil!")
    } else {
        fmt.Println("Interface is not nil.")
    }
}

func main() {
    var d Describer // zero value is nil
    checkNil(d)

    d = nil // explicitly set to nil
    checkNil(d)

    d = struct{ Describer }{} // non-nil value
    checkNil(d)
}
```
