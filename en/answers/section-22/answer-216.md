## 📘 Section: Go Modules and Dependency Management  
### 🔹 Category: go.mod and Dependency Management  
#### ✅ Answer 216: Replacing modules in go.mod

The `replace` directive in `go.mod` allows you to override a module dependency with a local path. This is useful for local development or testing changes before publishing.

Suppose you have a main module that depends on `example.com/mylib`. You can create a local version of `mylib` and use `replace` to point to it:

```go
// main.go
package main
import (
    "fmt"
    "example.com/mylib"
)
func main() {
    fmt.Println(mylib.Hello())
}
```

Your `go.mod` would include:

```
module example.com/myapp

require example.com/mylib v0.0.0

replace example.com/mylib => ../mylib
```

And in `../mylib/hello.go`:

```go
package mylib
func Hello() string {
    return "Hello from local mylib!"
}
```

Now, running your main program will use the local version of `mylib` instead of fetching it from a remote repository.
