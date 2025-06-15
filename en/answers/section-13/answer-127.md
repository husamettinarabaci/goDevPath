## 📘 Section: Packages and Imports  
### 🔹 Category: Exported vs Unexported Identifiers  
#### ✅ Answer 127: Exported vs unexported identifiers

In Go, identifiers that start with an uppercase letter are exported (public) and accessible from other packages, while those starting with a lowercase letter are unexported (private). Example:

```go
// mypkg/mypkg.go
package mypkg

var ExportedVar = "I am exported!"
var unexportedVar = "I am unexported!"
```

```go
// main.go
package main

import (
    "fmt"
    "mypkg"
)

func main() {
    fmt.Println(mypkg.ExportedVar)      // Accessible
    // fmt.Println(mypkg.unexportedVar) // Compile error: unexportedVar not accessible
}
```

Only `ExportedVar` is accessible from `main`. Attempting to access `unexportedVar` results in a compile-time error.
