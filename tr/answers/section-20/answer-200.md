## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: HTTP Sunucularında Hata Yönetimi  
#### ✅ Cevap 200: HTTP sunucularında hata yönetimi

Go'da HTTP sunucularında sağlam hata yönetimi, doğru durum kodlarının döndürülmesi ve hataların loglanması ile sağlanır. Aşağıda, bir route üzerinden hata tetiklenen ve sunucunun 500 durum kodu ile yanıt verdiği bir örnek bulunmaktadır:

```go
package main

import (
    "fmt"
    "log"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    // Hata simülasyonu (örneğin, kaynak bulunamadı veya sunucu hatası)
    err := fmt.Errorf("simüle edilen sunucu hatası")
    log.Printf("hata: %v", err) // Hata loglanıyor
    http.Error(w, "Dahili Sunucu Hatası", http.StatusInternalServerError)
}

func main() {
    http.HandleFunc("/", handler)
    log.Println("Sunucu http://localhost:8080 adresinde çalışıyor")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        log.Fatalf("sunucu başarısız: %v", err)
    }
}
```

Bu sunucu, hatayı loglar ve istemciye 500 Dahili Sunucu Hatası yanıtı gönderir.
