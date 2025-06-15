## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Building a REST API in Go  
#### ✅ Answer 242: Building a REST API in Go

A simple REST API in Go can be built using the `net/http` package. Here is an example with a `/hello` endpoint that returns a JSON response:

```go
package main

import (
    "encoding/json"
    "net/http"
)

type Message struct {
    Text string `json:"text"`
}

func helloHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != http.MethodGet {
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
        return
    }
    msg := Message{Text: "Hello, Go API!"}
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(msg)
}

func main() {
    http.HandleFunc("/hello", helloHandler)
    http.ListenAndServe(":8080", nil)
}
```

This program starts an HTTP server on port 8080. A GET request to `/hello` returns a JSON message. This is a basic pattern for building REST APIs in Go.
