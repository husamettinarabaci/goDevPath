## 📘 Section: Functions II  
### 🔹 Category: Scope, Closures, Recursion, Defer, Panic/Recover  
#### ✅ Answer 60: Functions as fields in structs

In Go, you can use functions as fields in structs by specifying the field type as a function signature. This allows you to assign different behaviors to struct instances.

```go
package main
import "fmt"

type Operator struct {
    op func(int, int) int
}

func main() {
    add := func(a, b int) int { return a + b }
    multiply := func(a, b int) int { return a * b }

    o1 := Operator{op: add}
    o2 := Operator{op: multiply}

    fmt.Println("Add:", o1.op(3, 4))        // Output: 7
    fmt.Println("Multiply:", o2.op(3, 4))   // Output: 12
}
```

Here, the `Operator` struct has a function field `op`, which can be assigned different functions and called through struct instances.
