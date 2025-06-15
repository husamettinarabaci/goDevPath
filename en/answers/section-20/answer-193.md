## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 193: Parsing JSON from HTTP responses

This program demonstrates how to make an HTTP GET request and parse the JSON response into a Go struct. The `net/http` package is used for the request, and `encoding/json` is used for decoding the response body.

```go
package main
import (
    "encoding/json"
    "fmt"
    "net/http"
)

type Response struct {
    Origin string `json:"origin"`
}

func main() {
    resp, err := http.Get("https://httpbin.org/get")
    if err != nil {
        fmt.Println("Request error:", err)
        return
    }
    defer resp.Body.Close()

    var result Response
    if err := json.NewDecoder(resp.Body).Decode(&result); err != nil {
        fmt.Println("Decode error:", err)
        return
    }

    fmt.Println("Origin:", result.Origin)
}
```
