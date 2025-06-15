## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: flag Paketi
#### ✅ Cevap 190: `flag` paketini kullanma

`flag` paketi, komut satırı argümanlarını ayrıştırmak için basit bir yol sunar. Flag'leri tanımlar, ayrıştırır ve ardından değerlerini kullanırsınız.

```go
package main
import (
    "flag"
    "fmt"
)

func main() {
    isim := flag.String("name", "GoDev", "isminiz")
    yas := flag.Int("age", 0, "yaşınız")
    flag.Parse()

    fmt.Println("İsim:", *isim)
    fmt.Println("Yaş:", *yas)
}
```
