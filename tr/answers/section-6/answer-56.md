## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 56: Go'da closure kullanımı

Go'da closure, fonksiyonun gövdesi dışında tanımlanan değişkenlere erişebilen fonksiyon değerleridir. Dış fonksiyon tamamlandıktan sonra bile bu değişkenlere erişebilir ve değiştirebilirler. Burada, `makeCounter` fonksiyonu bir closure döndürür ve sayaç değerini arttırır.

```go
package main
import "fmt"

func makeCounter() func() int {
    sayac := 0
    return func() int {
        sayac++
        return sayac
    }
}

func main() {
    sayac := makeCounter()
    fmt.Println(sayac()) // Çıktı: 1
    fmt.Println(sayac()) // Çıktı: 2
    fmt.Println(sayac()) // Çıktı: 3
}
```
