## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 194: Basit bir HTTP sunucusu oluşturma

Bu program, Go'da `net/http` paketi ile temel bir HTTP sunucusu oluşturmayı gösterir. Sunucu 8080 portunda dinler ve kök yola gelen isteklere "Hello, World!" yanıtı döner.

```go
package main
import (
    "fmt"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    http.HandleFunc("/", handler)
    fmt.Println("Sunucu http://localhost:8080 adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```
