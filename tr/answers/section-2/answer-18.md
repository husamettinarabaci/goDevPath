## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Sıfır Değerler  
#### ✅ Cevap 18: Go'da sıfır değerler

Go'da, tanımlanan ancak başlatılmayan değişkenlere varsayılan olarak "sıfır değer" atanır. Her tipin kendine özgü bir sıfır değeri vardır:
- `int`: 0
- `float64`: 0.0
- `string`: ""
- `bool`: false

Örnek:

```go
package main
import "fmt"

func main() {
    var a int
    var b float64
    var c string
    var d bool
    fmt.Println(a) // 0
    fmt.Println(b) // 0
    fmt.Println(c) // ""
    fmt.Println(d) // false
}
```
