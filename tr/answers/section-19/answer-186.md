## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: os Paketi
#### ✅ Cevap 186: `os` paketini kullanma

`os` paketi, işletim sistemiyle etkileşim için çeşitli fonksiyonlar sunar. Burada, geçerli dizin için `os.Getwd`, ortam değişkenleri için `os.Environ` ve dosya varlığı kontrolü için `os.Stat` kullanılmıştır.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    // Geçerli çalışma dizinini yazdır
    dizin, err := os.Getwd()
    if err != nil {
        fmt.Println("Çalışma dizini alınamadı:", err)
    } else {
        fmt.Println("Geçerli çalışma dizini:", dizin)
    }

    // Tüm ortam değişkenlerini listele
    fmt.Println("Ortam değişkenleri:")
    for _, env := range os.Environ() {
        fmt.Println(env)
    }

    // test.txt dosyası var mı kontrol et
    if _, err := os.Stat("test.txt"); err == nil {
        fmt.Println("test.txt mevcut.")
    } else if os.IsNotExist(err) {
        fmt.Println("test.txt mevcut değil.")
    } else {
        fmt.Println("test.txt kontrolünde hata:", err)
    }
}
```
