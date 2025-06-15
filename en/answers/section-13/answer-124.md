## 📘 Section: Packages and Imports  
### 🔹 Category: Using Package-Level Variables  
#### ✅ Answer 124: Using package-level variables

Package-level variables are declared outside of any function and are accessible throughout the package. Here, we use a package-level variable to keep track of a counter.

```go
package main

import "fmt"

var counter int = 0

func increment() {
    counter++
}

func main() {
    increment()
    fmt.Println(counter) // 1
    increment()
    fmt.Println(counter) // 2
    increment()
    fmt.Println(counter) // 3
}
```

This program declares a package-level variable `counter`, modifies it in a function, and prints its value after each increment.
