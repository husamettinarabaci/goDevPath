## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Web Utilities  
#### ✅ Answer 247: Building a URL shortener

This solution demonstrates a simple URL shortener web service in Go. It accepts long URLs via HTTP POST, generates a short code, stores the mapping in memory, and redirects users from the short URL to the original URL using HTTP GET. The implementation uses the `net/http` package.

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "math/rand"
    "net/http"
    "sync"
    "time"
)

var (
    urlMap = make(map[string]string)
    mu     sync.RWMutex
)

func generateCode(n int) string {
    letters := []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789")
    rand.Seed(time.Now().UnixNano())
    b := make([]rune, n)
    for i := range b {
        b[i] = letters[rand.Intn(len(letters))]
    }
    return string(b)
}

func shortenHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != http.MethodPost {
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
        return
    }
    var req struct{ URL string }
    if err := json.NewDecoder(r.Body).Decode(&req); err != nil || req.URL == "" {
        http.Error(w, "Invalid input", http.StatusBadRequest)
        return
    }
    code := generateCode(6)
    mu.Lock()
    urlMap[code] = req.URL
    mu.Unlock()
    fmt.Fprintf(w, "Short URL: http://localhost:8080/%s\n", code)
}

func redirectHandler(w http.ResponseWriter, r *http.Request) {
    code := r.URL.Path[1:]
    mu.RLock()
    url, ok := urlMap[code]
    mu.RUnlock()
    if !ok {
        http.NotFound(w, r)
        return
    }
    http.Redirect(w, r, url, http.StatusFound)
}

func main() {
    http.HandleFunc("/shorten", shortenHandler)
    http.HandleFunc("/", redirectHandler)
    fmt.Println("URL shortener running on :8080")
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```
