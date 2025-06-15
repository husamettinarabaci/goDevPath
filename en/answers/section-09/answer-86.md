## 📘 Section: Arrays and Slices  
### 🔹 Category: Slice Basics  
#### ✅ Answer 86: Appending to a slice

You can use the built-in `append` function to add elements to a slice in Go. Here is an example:

```go
package main
import "fmt"

func main() {
    nums := []int{1, 2, 3}
    nums = append(nums, 4, 5)
    fmt.Println(nums)
}
```

- `append(nums, 4, 5)` adds 4 and 5 to the end of the slice.
- The updated slice is printed.
