## 📘 Section: Arrays and Slices  
### 🔹 Category: Arrays and Slices  
#### ✅ Answer 82: Accessing and modifying array elements

To access or modify an element in a Go array, use the index (starting from 0). This example shows how to print and update the third element of an integer array.

```go
package main
import "fmt"

func main() {
    arr := [5]int{10, 20, 30, 40, 50}
    fmt.Println("Original third element:", arr[2]) // Index 2 is the third element
    arr[2] = 99 // Modify the third element
    fmt.Println("Updated array:", arr)
}
```
