## 📘 Section: Networking and HTTP
### 🔹 Category: HTTP GET Requests
#### ✅ Answer 191: Making HTTP GET requests

The `net/http` package allows you to make HTTP requests easily. Here, we use `http.Get` to send a GET request, then read the status code and body.

```go
package main
import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    resp, err := http.Get("https://api.github.com")
    if err != nil {
        fmt.Println("Request error:", err)
        return
    }
    defer resp.Body.Close()

    fmt.Println("Status Code:", resp.StatusCode)

    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println("Read body error:", err)
        return
    }
    fmt.Println("Body:", string(body))
}
```
