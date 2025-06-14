## 📘 Bölüm: Başlangıç  
### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
#### ✅ Cevap 3: Go'da `var` ve `const` arasındaki fark

Bu örnek, Go'da değişkenler ve sabitler arasındaki farkı gösterir. `var` ile tanımlanan değişkenler değiştirilebilirken, `const` ile tanımlanan sabitler ilk atamadan sonra değiştirilemez.

```go
package main
import "fmt"

func main() {
    var x = 10 // değişken: değiştirilebilir
    const y = 5 // sabit: değiştirilemez
    fmt.Println("Değişken x:", x)
    fmt.Println("Sabit y:", y)
}
```
