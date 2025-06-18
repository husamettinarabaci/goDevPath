## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Rune ve Byte Tipleri  
#### ✅ Cevap 20: `rune` ve `byte` tiplerini kullanma

Go'da `byte`, `uint8` için bir takma addır ve genellikle ASCII karakterleri temsil etmek için kullanılır. `rune` ise `int32` için bir takma addır ve Unicode karakterleri için kullanılır. Örnek:

```go
package main
import "fmt"

func main() {
    var b byte = 'A'
    var r rune = '✓'
    fmt.Printf("b: %c, type: %T\n", b, b)
    fmt.Printf("r: %c, type: %T\n", r, r)
}
```
