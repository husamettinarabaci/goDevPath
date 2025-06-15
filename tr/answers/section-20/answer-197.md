## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 197: URL parametrelerini kullanma

Bu program, Go'da `net/http` paketi ile bir HTTP sunucusunda URL sorgu parametrelerini okumayı gösterir. Sunucu 8080 portunda dinler ve `/greet?name=Isminiz` isteğine kişiselleştirilmiş bir selamlama döner.

```go
package main
import (
    "fmt"
    "net/http"
)

func selamlaHandler(w http.ResponseWriter, r *http.Request) {
    name := r.URL.Query().Get("name")
    if name == "" {
        name = "Guest"
    }
    fmt.Fprintf(w, "Hello, %s!", name)
}

func main() {
    http.HandleFunc("/greet", selamlaHandler)
    fmt.Println("Sunucu http://localhost:8080 adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```
