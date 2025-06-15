## 📘 Section: Arrays and Slices  
### 🔹 Category: Array Basics  
#### ✅ Answer 83: Iterating over arrays with `for`

To iterate over an array in Go, you can use a `for` loop with an index or the `range` keyword. Here is an example using both methods:

```go
package main
import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    // Using index
    for i := 0; i < len(arr); i++ {
        fmt.Println(arr[i])
    }
    // Using range
    for _, v := range arr {
        fmt.Println(v)
    }
}
```

- The first loop uses an index to access each element.
- The second loop uses `range` to iterate over values directly.
