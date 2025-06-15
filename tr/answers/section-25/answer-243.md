## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Eşzamanlı web scraper geliştirme  
#### ✅ Cevap 243: Eşzamanlı web scraper geliştirme

Go'da eşzamanlı bir web scraper, goroutine ve kanallar kullanılarak birden fazla URL'nin paralel olarak çekilmesini sağlar. İşte basit bir örnek:

```go
package main

import (
    "fmt"
    "net/http"
)

func cek(url string, ch chan<- string) {
    resp, err := http.Get(url)
    if err != nil {
        ch <- fmt.Sprintf("%s: hata: %v", url, err)
        return
    }
    ch <- fmt.Sprintf("%s: %d", url, resp.StatusCode)
    resp.Body.Close()
}

func main() {
    urller := []string{
        "https://www.google.com",
        "https://www.golang.org",
        "https://www.github.com",
    }
    ch := make(chan string)
    for _, url := range urller {
        go cek(url, ch)
    }
    for range urller {
        fmt.Println(<-ch)
    }
}
```

Bu program, her URL için bir goroutine başlatır, HTTP durum kodunu çeker ve sonuçları kanal üzerinden yazdırır.
