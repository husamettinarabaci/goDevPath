## 📘 Section: Standard Library Essentials
### 🔹 Category: io and io/ioutil Packages
#### ✅ Answer 187: Using the `io` and `io/ioutil` packages

The `io` and `io/ioutil` packages provide convenient functions for file I/O. In Go 1.16+, `os.ReadFile` and `os.WriteFile` are preferred, but `ioutil.ReadFile` and `ioutil.WriteFile` are still widely used.

```go
package main
import (
    "fmt"
    "io/ioutil"
)

func main() {
    // Read all contents of input.txt
    data, err := ioutil.ReadFile("input.txt")
    if err != nil {
        fmt.Println("Error reading file:", err)
    } else {
        fmt.Println("File contents:", string(data))
    }

    // Write to output.txt
    err = ioutil.WriteFile("output.txt", []byte("Hello, Go!"), 0644)
    if err != nil {
        fmt.Println("Error writing file:", err)
    } else {
        fmt.Println("Successfully wrote to output.txt")
    }
}
```
