## 📘 Section: Deployment and Tooling  
### 🔹 Category: Building, cross-compiling, Docker, CI  
#### ✅ Answer 223: Using environment variables

You can use the `os` package in Go to read environment variables. The `os.Getenv` function retrieves the value of an environment variable. Set the variable in your shell before running the program.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    name := os.Getenv("MY_NAME")
    if name == "" {
        fmt.Println("MY_NAME is not set.")
    } else {
        fmt.Printf("Hello, %s!\n", name)
    }
}
```

Set and run in the terminal:

```bash
export MY_NAME=GoDev
go run main.go
```
