## 📘 Section: Pointers and Memory  
### 🔹 Category: Using the `make` function  
#### ✅ Answer 67: Using the `make` function

The `make` function in Go is used to initialize slices, maps, and channels. Here, we use `make` to create a slice of integers with a specific length and capacity, assign values, and print the slice along with its length and capacity.

```go
package main
import "fmt"

func main() {
    s := make([]int, 3, 5) // slice of int, length 3, capacity 5
    s[0] = 10
    s[1] = 20
    s[2] = 30
    fmt.Println(s)         // prints: [10 20 30]
    fmt.Println(len(s))    // prints: 3
    fmt.Println(cap(s))    // prints: 5
}
```
