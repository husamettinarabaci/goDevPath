## 📘 Section: Arrays and Slices  
### 🔹 Category: Slice Basics  
#### ✅ Answer 87: Copying slices

The built-in `copy` function in Go copies elements from one slice to another. Here is an example:

```go
package main
import "fmt"

func main() {
    src := []int{10, 20, 30, 40}
    dst := make([]int, len(src))
    copy(dst, src)
    fmt.Println("Source slice:", src)
    fmt.Println("Destination slice:", dst)
}
```

- `make([]int, len(src))` creates a new slice with the same length as `src`.
- `copy(dst, src)` copies the contents.
- Printing both slices verifies the copy.
