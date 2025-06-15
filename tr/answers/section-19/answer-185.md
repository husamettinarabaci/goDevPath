## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: math/rand Paketi
#### ✅ Cevap 185: Rastgele Sayı Üretimi

`math/rand` paketi, sahte rastgele sayılar üretmek için fonksiyonlar sağlar. Sabit bir seed ile başlatmak, çıktının tekrarlanabilir olmasını sağlar.

```go
package main
import (
    "fmt"
    "math/rand"
    "time"
)

func main() {
    rand.Seed(time.Now().UnixNano()) // Her çalıştırmada farklı sonuçlar için
    rastgeleSayi := rand.Intn(100)   // 0 <= n < 100
    rastgeleOndalik := rand.Float64() // 0.0 <= f < 1.0

    fmt.Println("Rastgele tamsayı:", rastgeleSayi)
    fmt.Println("Rastgele ondalık:", rastgeleOndalik)

    // Sabit seed ile tekrarlanabilir sonuçlar
    rand.Seed(42)
    fmt.Println("Seed ile rastgele tamsayı:", rand.Intn(100))
}
```
