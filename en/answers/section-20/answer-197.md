## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 197: Using URL parameters

This program demonstrates how to read URL query parameters in a Go HTTP server using the `net/http` package. The server listens on port 8080 and responds to `/greet?name=YourName` with a personalized greeting.

```go
package main
import (
    "fmt"
    "net/http"
)

func greetHandler(w http.ResponseWriter, r *http.Request) {
    name := r.URL.Query().Get("name")
    if name == "" {
        name = "Guest"
    }
    fmt.Fprintf(w, "Hello, %s!", name)
}

func main() {
    http.HandleFunc("/greet", greetHandler)
    fmt.Println("Server started at http://localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Server error:", err)
    }
}
```
