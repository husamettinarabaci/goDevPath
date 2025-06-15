## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Go ile REST API geliştirme  
#### ✅ Cevap 242: Go ile REST API geliştirme

Go'da basit bir REST API, `net/http` paketi ile oluşturulabilir. Aşağıda `/merhaba` endpoint'i ile JSON yanıtı döndüren bir örnek verilmiştir:

```go
package main

import (
    "encoding/json"
    "net/http"
)

type Mesaj struct {
    Metin string `json:"metin"`
}

func merhabaHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != http.MethodGet {
        http.Error(w, "Yalnızca GET metodu destekleniyor", http.StatusMethodNotAllowed)
        return
    }
    msg := Mesaj{Metin: "Merhaba, Go API!"}
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(msg)
}

func main() {
    http.HandleFunc("/merhaba", merhabaHandler)
    http.ListenAndServe(":8080", nil)
}
```

Bu program 8080 portunda bir HTTP sunucusu başlatır. `/merhaba` endpoint'ine GET isteği gönderildiğinde JSON mesajı döner. Bu, Go ile REST API geliştirmenin temel bir örneğidir.
