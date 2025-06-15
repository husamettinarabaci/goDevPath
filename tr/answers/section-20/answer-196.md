## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 196: Statik dosya sunma

Bu program, Go'da `net/http` paketi ve `http.FileServer` ile statik dosya sunmayı gösterir. Sunucu 8080 portunda dinler ve `/static/dosyaadi` isteklerinde ilgili dosyayı `static` dizininden sunar.

```go
package main
import (
    "fmt"
    "net/http"
)

func main() {
    fs := http.FileServer(http.Dir("static"))
    http.Handle("/static/", http.StripPrefix("/static/", fs))
    fmt.Println("Sunucu http://localhost:8080 adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```
