## 📘 Bölüm: Mapler  
### 🔹 Kategori: Mapler  
#### ✅ Cevap 99: Map ve sıfır değerler

Go'da bir map'in sıfır değeri `nil`'dir. Nil bir map'in anahtarı yoktur, değer saklayamaz ve başlatılmış (ama boş) bir map'ten farklı davranır. Map'in nil olup olmadığını basit bir karşılaştırma ile kontrol edebilirsiniz. Örnek:

```go
package main
import "fmt"

func main() {
    var m map[string]int // sıfır değeri nil'dir
    if m == nil {
        fmt.Println("Map nil.")
    } else {
        fmt.Println("Map nil değil.")
    }
}
```
