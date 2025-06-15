## 📘 Section: Advanced Go Features  
### 🔹 Category: Generics  
#### ✅ Answer 206: Using generics (Go 1.18+)

Generics in Go (introduced in 1.18) allow you to write functions and types that work with any type. Here is an example of a generic function that returns the first element of a slice:

```go
package main
import "fmt"

func First[T any](s []T) T {
    return s[0]
}

func main() {
    ints := []int{1, 2, 3}
    strings := []string{"a", "b", "c"}
    fmt.Println(First(ints))    // Output: 1
    fmt.Println(First(strings)) // Output: a
}
```
