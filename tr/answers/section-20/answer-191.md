## 📘 Bölüm: Ağ ve HTTP
### 🔹 Kategori: HTTP GET İstekleri
#### ✅ Cevap 191: HTTP GET isteği yapma

`net/http` paketi ile kolayca HTTP istekleri yapılabilir. Burada, `http.Get` ile GET isteği gönderiliyor, ardından durum kodu ve gövde okunuyor.

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
        fmt.Println("İstek hatası:", err)
        return
    }
    defer resp.Body.Close()

    fmt.Println("Durum Kodu:", resp.StatusCode)

    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println("Gövde okuma hatası:", err)
        return
    }
    fmt.Println("Gövde:", string(body))
}
```
