## 📘 Section: Networking and HTTP  
### 🔹 Category: Making HTTP Requests  
#### ✅ Answer 192: Making HTTP POST requests

To send an HTTP POST request with a JSON payload in Go, use the `net/http` and `encoding/json` packages. Marshal your data to JSON, create a POST request with the correct headers, and read the response body.

```go
package main

import (
    "bytes"
    "encoding/json"
    "fmt"
    "io/ioutil"
    "net/http"
)

type Payload struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
}

func main() {
    url := "https://httpbin.org/post"
    data := Payload{Name: "Alice", Age: 30}
    jsonData, err := json.Marshal(data)
    if err != nil {
        panic(err)
    }

    resp, err := http.Post(url, "application/json", bytes.NewBuffer(jsonData))
    if err != nil {
        panic(err)
    }
    defer resp.Body.Close()

    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        panic(err)
    }
    fmt.Println(string(body))
}
```
