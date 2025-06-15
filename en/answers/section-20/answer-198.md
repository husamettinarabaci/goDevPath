## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 198: Handling forms in HTTP

This program demonstrates how to serve an HTML form and handle form submissions in Go using the `net/http` package. The server listens on port 8080, serves a form at `/`, and displays submitted data at `/submit`.

```go
package main
import (
    "fmt"
    "net/http"
)

func formHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprint(w, `<form action="/submit" method="post">
        Name: <input type="text" name="name">
        <input type="submit" value="Submit">
    </form>`)
}

func submitHandler(w http.ResponseWriter, r *http.Request) {
    if err := r.ParseForm(); err != nil {
        fmt.Fprintln(w, "ParseForm() error:", err)
        return
    }
    name := r.FormValue("name")
    fmt.Fprintf(w, "Hello, %s!", name)
}

func main() {
    http.HandleFunc("/", formHandler)
    http.HandleFunc("/submit", submitHandler)
    fmt.Println("Server started at http://localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Server error:", err)
    }
}
```
