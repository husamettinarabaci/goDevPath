## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: HTTP İstekleri Yapma  
#### ✅ Cevap 192: HTTP POST isteği yapma

Go'da JSON veri ile bir HTTP POST isteği göndermek için `net/http` ve `encoding/json` paketleri kullanılır. Verinizi JSON'a dönüştürüp, uygun başlıklarla POST isteği oluşturun ve yanıt gövdesini okuyun.

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
