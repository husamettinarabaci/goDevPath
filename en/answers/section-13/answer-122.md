## 📘 Section: Packages and Imports  
### 🔹 Category: Importing Standard Library Packages  
#### ✅ Answer 122: Importing standard library packages

To use a standard library package in Go, import it at the top of your file and call its exported functions. Here, we use the `math` package to calculate a square root.

```go
package main

import (
    "fmt"
    "math"
)

func main() {
    result := math.Sqrt(16)
    fmt.Println(result)
}
```

This program imports the `math` package and uses `math.Sqrt` to compute the square root of 16, printing the result.
