## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointers to arrays and slices  
#### ✅ Answer 68: Pointers to arrays and slices

In Go, you can create pointers to arrays, and slices provide reference semantics to the underlying array. Here, we demonstrate modifying an array via a pointer and how a slice reflects changes to the array.

```go
package main
import "fmt"

func main() {
    arr := [3]int{1, 2, 3}
    p := &arr           // pointer to array
    (*p)[0] = 10        // modify via pointer
    fmt.Println(arr)    // prints: [10 2 3]

    s := arr[:]
    s[1] = 20           // modify via slice
    fmt.Println(arr)    // prints: [10 20 3]
}
```
