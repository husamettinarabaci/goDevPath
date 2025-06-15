## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 195: HTTP sunucusunda route yönetimi

Bu program, Go'da `net/http` paketi ile bir HTTP sunucusunda birden fazla route yönetimini gösterir. Sunucu 8080 portunda dinler ve `/` ile `/about` yollarına farklı yanıtlar döner.

```go
package main
import (
    "fmt"
    "net/http"
)

func anasayfaHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Welcome!")
}

func hakkindaHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "About Page")
}

func main() {
    http.HandleFunc("/", anasayfaHandler)
    http.HandleFunc("/about", hakkindaHandler)
    fmt.Println("Sunucu http://localhost:8080 adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```
