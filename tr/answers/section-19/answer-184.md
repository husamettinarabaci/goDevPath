## 📘 Bölüm: Standart Kütüphane Temelleri  
### 🔹 Kategori: math Paketi  
#### ✅ Cevap 184: `math` paketini kullanma

Go'daki `math` paketi, temel sabitler ve matematiksel fonksiyonlar sağlar. Burada, 16'nın karekökünü hesaplamak için `math.Sqrt` ve Pi sayısının değerini almak için `math.Pi` kullanıyoruz.

```go
package main
import (
    "fmt"
    "math"
)

func main() {
    sqrt := math.Sqrt(16)
    pi := math.Pi
    fmt.Println("16'nın karekökü:", sqrt)
    fmt.Println("Pi sayısı:", pi)
}
```
