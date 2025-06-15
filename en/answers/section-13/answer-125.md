## 📘 Section: Packages and Imports  
### 🔹 Category: Using Package-Level Functions  
#### ✅ Answer 125: Using package-level functions

Package-level functions are defined outside of any type and can be called from anywhere in the same package. Here, we define a `Greet` function and use it in `main`.

```go
package main

import "fmt"

func Greet(name string) string {
    return "Hello, " + name + "!"
}

func main() {
    fmt.Println(Greet("Alice"))
    fmt.Println(Greet("Bob"))
}
```

This program defines a package-level function `Greet` and calls it with different names, printing the results.
