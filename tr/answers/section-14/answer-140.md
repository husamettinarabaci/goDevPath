## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: error tipi, özel hatalar, panic/recover  
#### ✅ Cevap 140: Kütüphanelerde hata yönetimi

Go kütüphanelerinde, fonksiyonlar hataları dahili olarak yönetmek yerine çağırana döndürmelidir. Kütüphaneyi kullanan kişi, hatayı kontrol edip yönetmekten sorumludur.

Örnek:

```go
// kutuphane/kutuphane.go
package kutuphane
import "errors"

func GorevYap(girdi int) error {
    if girdi < 0 {
        return errors.New("girdi negatif olamaz")
    }
    return nil
}
```

```go
// main.go
package main
import (
    "fmt"
    "kutuphane"
)

func main() {
    err := kutuphane.GorevYap(-1)
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    fmt.Println("Görev başarıyla tamamlandı")
}
```
