## 📘 Section: Advanced Go Features  
### 🔹 Category: Unsafe Package  
#### ✅ Answer 202: Using `unsafe` package

The `unsafe` package in Go allows low-level memory manipulation. Here, we use it to get the size of a struct and convert a pointer to an integer type.

```go
package main
import (
    "fmt"
    "unsafe"
)

type Data struct {
    A int32
    B float64
}

func main() {
    d := Data{42, 3.14}
    fmt.Println("Size of Data struct:", unsafe.Sizeof(d))
    ptr := &d
    uptr := uintptr(unsafe.Pointer(ptr))
    fmt.Printf("Pointer as uintptr: %x\n", uptr)
}
```
