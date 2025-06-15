## 📘 Section: Arrays and Slices  
### 🔹 Category: Slice Basics  
#### ✅ Answer 85: Declaring and initializing slices

In Go, you can declare and initialize a slice using a composite literal. Here is an example:

```go
package main
import "fmt"

func main() {
    fruits := []string{"apple", "banana", "cherry"}
    fmt.Println(fruits)
}
```

- `[]string{"apple", "banana", "cherry"}` creates a slice of strings with three elements.
- Printing the slice displays its contents.
