## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Boolean Tipler  
#### ✅ Cevap 17: Boolean değişken oluşturma ve kullanma

Go'da boolean değişkenler `bool` tipiyle tanımlanır. `true` veya `false` değerleri atanabilir ve `fmt.Println` ile ekrana yazdırılabilir.

```go
package main
import "fmt"

func main() {
    var aktifMi bool = true
    fmt.Println(aktifMi) // Çıktı: true
    aktifMi = false
    fmt.Println(aktifMi) // Çıktı: false
}
```
