## 📘 Section: Networking and HTTP  
### 🔹 Category: Error Handling in HTTP Servers  
#### ✅ Answer 200: Error handling in HTTP servers

In Go, robust error handling in HTTP servers involves returning the correct status codes and logging errors for debugging. Here is an example where a route triggers an error and the server responds with a 500 status code and logs the error:

```go
package main

import (
    "fmt"
    "log"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    // Simulate an error (e.g., resource not found or internal error)
    err := fmt.Errorf("simulated server error")
    log.Printf("error: %v", err) // Log the error
    http.Error(w, "Internal Server Error", http.StatusInternalServerError)
}

func main() {
    http.HandleFunc("/", handler)
    log.Println("Server running on http://localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        log.Fatalf("server failed: %v", err)
    }
}
```

This server logs the error and sends a 500 Internal Server Error response to the client.
