## 📘 Section: Arrays and Slices  
### 🔹 Category: Arrays and Slices  
#### ✅ Answer 90: Using the `len` and `cap` functions

The `len` function returns the number of elements in an array or slice, while `cap` returns the capacity (maximum size before reallocation for slices). For arrays, length and capacity are always the same. For slices, capacity can be greater than length and grows as you append elements.

```go
package main
import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    slc := []int{1, 2, 3}

    fmt.Println("Array:", arr)
    fmt.Println("len(arr):", len(arr))
    fmt.Println("cap(arr):", cap(arr))

    fmt.Println("Slice:", slc)
    fmt.Println("len(slc):", len(slc))
    fmt.Println("cap(slc):", cap(slc))

    slc = append(slc, 4, 5, 6)
    fmt.Println("After appending:", slc)
    fmt.Println("len(slc):", len(slc))
    fmt.Println("cap(slc):", cap(slc))
}
```
