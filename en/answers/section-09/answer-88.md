## 📘 Section: Arrays and Slices  
### 🔹 Category: Slice Basics  
#### ✅ Answer 88: Slices and underlying arrays

Slices in Go are backed by underlying arrays. Modifying a slice changes the underlying array. Example:

```go
package main
import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    s := arr[1:4] // 2nd to 4th elements: 2, 3, 4
    s[0] = 99     // Modify first element of the slice
    fmt.Println("Array:", arr)
    fmt.Println("Slice:", s)
}
```

- Changing `s[0]` updates `arr[1]` because the slice shares the same underlying array.
- Output:
  - `Array: [1 99 3 4 5]`
  - `Slice: [99 3 4]`
