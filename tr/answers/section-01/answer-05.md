## 📘 Bölüm: Başlangıç  
### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
#### ✅ Cevap 5: Sayı tiplerini tip dönüşümü ile dönüştürme

Bu örnek, Go'da bir tamsayının `float64` tipine tip dönüşümü ile nasıl dönüştürüleceğini gösterir. Tip dönüşümü, hedef tip parantez içinde belirtilerek yapılır.

```go
package main
import "fmt"

func main() {
    var i int = 42
    var f float64 = float64(i) // tip dönüşümü
    fmt.Println("Tamsayı:", i)
    fmt.Println("Float64:", f)
}
```
