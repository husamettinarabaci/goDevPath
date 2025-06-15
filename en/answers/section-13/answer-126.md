## 📘 Section: Packages and Imports  
### 🔹 Category: Package Initialization with `init`  
#### ✅ Answer 126: Package initialization with `init`

The `init` function in Go is called automatically before the `main` function, making it useful for initialization tasks. Here is an example:

```go
package main

import "fmt"

func init() {
    fmt.Println("Initializing package...")
}

func main() {
    fmt.Println("main function running")
}
```

When you run this program, the message from `init` is printed before the message from `main`, demonstrating the order of execution.
