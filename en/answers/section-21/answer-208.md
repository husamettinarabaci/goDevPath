## 📘 Section: Advanced Go Features  
### 🔹 Category: Function Types and Callbacks  
#### ✅ Answer 208: Using function types and callbacks

Function types in Go allow you to define variables, fields, or parameters that can hold functions with a specific signature. Callbacks are functions passed as arguments to other functions, enabling flexible and reusable code. This is commonly used for event handling, custom sorting, or processing collections.

In the example below, we define a function type `Operation`, implement two functions (`add` and `multiply`) matching that type, and write a `compute` function that takes an `Operation` as a callback:

```go
package main
import "fmt"

// Define a function type
 type Operation func(int, int) int

// Implement two functions matching the type
func add(a, b int) int {
    return a + b
}

func multiply(a, b int) int {
    return a * b
}

// Function that takes a callback
func compute(a, b int, op Operation) int {
    return op(a, b)
}

func main() {
    fmt.Println("Add:", compute(3, 4, add))         // Output: Add: 7
    fmt.Println("Multiply:", compute(3, 4, multiply)) // Output: Multiply: 12
    // Using an anonymous function as a callback
    result := compute(10, 5, func(x, y int) int {
        return x - y
    })
    fmt.Println("Subtract:", result) // Output: Subtract: 5
}
```
