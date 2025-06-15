## 📘 Section: Packages and Imports  
### 🔹 Category: Importing Third-Party Packages  
#### ✅ Answer 123: Importing third-party packages

To use a third-party package in Go, install it with `go get`, import it, and use its functions. Here, we use the `github.com/fatih/color` package to print colored text.

First, install the package:

```sh
go get github.com/fatih/color
```

Then, use it in your code:

```go
package main

import (
    "github.com/fatih/color"
)

func main() {
    color.Cyan("This is a cyan message!")
}
```

This program prints a message in cyan color using the third-party `color` package.
