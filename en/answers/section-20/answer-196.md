## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 196: Serving static files

This program demonstrates how to serve static files in Go using the `net/http` package and `http.FileServer`. The server listens on port 8080 and serves files from the `static` directory for requests to `/static/filename`.

```go
package main
import (
    "fmt"
    "net/http"
)

func main() {
    fs := http.FileServer(http.Dir("static"))
    http.Handle("/static/", http.StripPrefix("/static/", fs))
    fmt.Println("Server started at http://localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Server error:", err)
    }
}
```
