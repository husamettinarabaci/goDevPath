## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 194: Creating a simple HTTP server

This program demonstrates how to create a basic HTTP server in Go using the `net/http` package. The server listens on port 8080 and responds with "Hello, World!" to requests at the root path.

```go
package main
import (
    "fmt"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    http.HandleFunc("/", handler)
    fmt.Println("Server started at http://localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Server error:", err)
    }
}
```
