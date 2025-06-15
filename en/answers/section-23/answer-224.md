## 📘 Section: Deployment and Tooling  
### 🔹 Category: Building, cross-compiling, Docker, CI  
#### ✅ Answer 224: Embedding assets in binaries

Go 1.16+ provides the `embed` package to embed static files into the binary. Use a special comment to specify the file, and declare a variable of type `embed.FS` or `[]byte`.

Suppose you have a file named `message.txt`:

```go
package main
import (
    "embed"
    "fmt"
)

//go:embed message.txt
var message string

func main() {
    fmt.Println(message)
}
```

When you build and run this program, the contents of `message.txt` will be printed, even if the file is not present at runtime.
