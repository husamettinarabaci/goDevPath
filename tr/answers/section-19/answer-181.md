## 📘 Bölüm: Standart Kütüphane Temelleri  
### 🔹 Kategori: `fmt` paketini kullanma  
#### ✅ Cevap 181: `fmt` paketini kullanma

Go'da `fmt` paketi, biçimlendirilmiş giriş/çıkış işlemleri sağlar. `fmt.Printf` fonksiyonu, `%s` (string), `%d` (tam sayı) ve `%f` (ondalık sayı) gibi format belirteçleriyle değerleri yazdırmanıza olanak tanır.

Örnek:

```go
package main
import "fmt"

func main() {
    isim := "Go"
    yas := 15
    pi := 3.14159
    fmt.Printf("İsim: %s\n", isim)         // string
    fmt.Printf("Yaş: %d\n", yas)           // tam sayı
    fmt.Printf("Pi: %f\n", pi)             // ondalık (varsayılan 6 basamak)
    fmt.Printf("Pi (2 basamak): %.2f\n", pi) // 2 ondalık basamakla
}
```

Bu program, `fmt` paketiyle farklı tipteki değerlerin biçimlendirilmiş çıktısını gösterir.
