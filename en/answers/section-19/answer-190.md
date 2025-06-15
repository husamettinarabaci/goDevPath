## 📘 Section: Standard Library Essentials
### 🔹 Category: flag Package
#### ✅ Answer 190: Using the `flag` package

The `flag` package provides a simple way to parse command-line arguments. You define flags, parse them, and then use their values in your program.

```go
package main
import (
    "flag"
    "fmt"
)

func main() {
    name := flag.String("name", "GoDev", "your name")
    age := flag.Int("age", 0, "your age")
    flag.Parse()

    fmt.Println("Name:", *name)
    fmt.Println("Age:", *age)
}
```
