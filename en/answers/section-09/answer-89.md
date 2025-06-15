## 📘 Section: Arrays and Slices  
### 🔹 Category: Multidimensional Arrays and Slices  
#### ✅ Answer 89: Multidimensional arrays and slices

Go supports both multidimensional arrays and slices. Here is how you can use them:

```go
package main
import "fmt"

func main() {
    // 2D array (3x2)
    arr := [3][2]int{{1, 2}, {3, 4}, {5, 6}}
    fmt.Println("2D array:")
    for i := 0; i < 3; i++ {
        for j := 0; j < 2; j++ {
            fmt.Print(arr[i][j], " ")
        }
        fmt.Println()
    }
    // 2D slice
    slice := [][]int{{7, 8}, {9, 10}}
    fmt.Println("2D slice:")
    for i := range slice {
        for j := range slice[i] {
            fmt.Print(slice[i][j], " ")
        }
        fmt.Println()
    }
}
```

- The array is declared as `[3][2]int` and initialized with values.
- The slice is declared as `[][]int` and also initialized.
- Nested loops print all elements.
