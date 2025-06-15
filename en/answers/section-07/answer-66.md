## 📘 Section: Pointers and Memory  
### 🔹 Category: Using the `new` function  
#### ✅ Answer 66: Using the `new` function

The `new` function in Go allocates memory for a variable and returns a pointer to it. Here, we use `new(int)` to get a pointer to an `int`, assign a value through the pointer, and print both the value and its address.

```go
package main
import "fmt"

func main() {
    p := new(int)      // allocate memory for an int, p is of type *int
    *p = 42            // assign value via pointer
    fmt.Println("Value:", *p)
    fmt.Println("Address:", p)
}
```
