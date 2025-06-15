## 📘 Section: Arrays and Slices  
### 🔹 Category: Array Basics  
#### ✅ Answer 84: Slicing arrays to create slices

You can create a slice from an array in Go using the slicing syntax `array[start:end]`. The start index is inclusive, the end index is exclusive.

```go
package main
import "fmt"

func main() {
    arr := [6]int{10, 20, 30, 40, 50, 60}
    slice := arr[1:4] // 2nd to 4th elements: 20, 30, 40
    fmt.Println("Original array:", arr)
    fmt.Println("Slice:", slice)
}
```

- `arr[1:4]` creates a slice from index 1 (inclusive) to 4 (exclusive), i.e., elements 20, 30, 40.
