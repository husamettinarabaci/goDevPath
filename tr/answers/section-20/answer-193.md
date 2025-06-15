## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 193: HTTP yanıtından JSON ayrıştırma

Bu program, HTTP GET isteği yapıp dönen JSON yanıtını bir Go struct'ına ayrıştırmayı gösterir. `net/http` paketi istek için, `encoding/json` ise yanıtı ayrıştırmak için kullanılır.

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
        fmt.Println("İstek hatası:", err)
        return
    }
    defer resp.Body.Close()

    var sonuc Response
    if err := json.NewDecoder(resp.Body).Decode(&sonuc); err != nil {
        fmt.Println("Ayrıştırma hatası:", err)
        return
    }

    fmt.Println("Origin:", sonuc.Origin)
}
```
