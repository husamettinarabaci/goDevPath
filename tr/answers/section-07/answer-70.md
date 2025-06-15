## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer'ı çözümleme (dereference)  
#### ✅ Cevap 70: Pointer'ı çözümleme (dereference)

Pointer'ı çözümlemek, pointer'ın gösterdiği adresteki değere erişmek anlamına gelir. Burada, `*` operatörü ile pointer üzerinden değer atıyor ve okuyoruz.

```go
package main
import "fmt"

func main() {
    var x int
    p := &x        // x'in adresi
    *p = 42        // pointer ile değer ata
    fmt.Println(x) // çıktı: 42
    fmt.Println(*p) // çıktı: 42
}
```
