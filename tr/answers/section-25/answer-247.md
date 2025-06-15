## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Web Araçları  
#### ✅ Cevap 247: URL kısaltıcı geliştirme

Bu çözüm, Go'da basit bir URL kısaltıcı web servisinin nasıl geliştirileceğini gösterir. Uzun URL'ler HTTP POST ile alınır, kısa bir kod üretilir, eşleşme bellekte saklanır ve kısa URL'ye gelen istekler orijinal adrese yönlendirilir. Uygulama `net/http` paketini kullanır.

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "math/rand"
    "net/http"
    "sync"
    "time"
)

var (
    urlMap = make(map[string]string)
    mu     sync.RWMutex
)

func generateCode(n int) string {
    letters := []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789")
    rand.Seed(time.Now().UnixNano())
    b := make([]rune, n)
    for i := range b {
        b[i] = letters[rand.Intn(len(letters))]
    }
    return string(b)
}

func shortenHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != http.MethodPost {
        http.Error(w, "Yalnızca POST yöntemi desteklenir", http.StatusMethodNotAllowed)
        return
    }
    var req struct{ URL string }
    if err := json.NewDecoder(r.Body).Decode(&req); err != nil || req.URL == "" {
        http.Error(w, "Geçersiz giriş", http.StatusBadRequest)
        return
    }
    code := generateCode(6)
    mu.Lock()
    urlMap[code] = req.URL
    mu.Unlock()
    fmt.Fprintf(w, "Kısa URL: http://localhost:8080/%s\n", code)
}

func redirectHandler(w http.ResponseWriter, r *http.Request) {
    code := r.URL.Path[1:]
    mu.RLock()
    url, ok := urlMap[code]
    mu.RUnlock()
    if !ok {
        http.NotFound(w, r)
        return
    }
    http.Redirect(w, r, url, http.StatusFound)
}

func main() {
    http.HandleFunc("/shorten", shortenHandler)
    http.HandleFunc("/", redirectHandler)
    fmt.Println("URL kısaltıcı :8080 portunda çalışıyor")
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```
