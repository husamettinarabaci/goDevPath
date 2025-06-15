## 📘 Section: Structs  
### 🔹 Category: Defining a struct and creating an instance  
#### ✅ Answer 71: Defining a struct and creating an instance

In Go, structs are used to group related data together. Here, we define a `Book` struct, create an instance, assign values to its fields, and print the struct.

```go
package main
import "fmt"

type Book struct {
    title string
    pages int
}

func main() {
    b := Book{"The Go Programming Language", 380}
    fmt.Println(b)
}
```
