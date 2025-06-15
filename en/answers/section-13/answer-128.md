## 📘 Section: Packages and Imports  
### 🔹 Category: Aliasing Imports  
#### ✅ Answer 128: Aliasing imports

You can assign an alias to an imported package in Go by specifying the alias before the import path. This is useful for shortening package names or resolving naming conflicts.

```go
package main

import f "fmt"

func main() {
    f.Println("Hello with alias!")
}
```

Here, the `fmt` package is imported as `f`, and all its functions are accessed using the `f` prefix.
