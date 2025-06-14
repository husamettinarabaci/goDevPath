## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Tip Dönüşümü  
#### ✅ Cevap 19: Sayısal tipler arasında dönüşüm

Go'da sayısal tipler arasında açık tip dönüşümü yapılabilir. Örnek:

```go
package main
import "fmt"

func main() {
    var a int = 42
    var b float64 = float64(a)
    fmt.Println(b) // 42.0
    var c int = int(b)
    fmt.Println(c) // 42
}
```
