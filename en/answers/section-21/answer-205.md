## 📘 Section: Advanced Go Features  
### 🔹 Category: Embedding Files with `embed` Package  
#### ✅ Answer 205: Embedding files with `embed` package

The `embed` package allows you to embed files into your Go binary at compile time. Here is an example:

Create a file named `hello.txt` with the following content:
```
Hello from embedded file!
```

Then, use the `embed` package in your Go program:

```go
package main
import (
    "embed"
    "fmt"
)

//go:embed hello.txt
var helloFile string

func main() {
    fmt.Print(helloFile)
}
```

When you run the program, it prints the contents of `hello.txt` using the embedded data.
