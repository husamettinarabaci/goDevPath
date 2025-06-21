## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Struct Karşılaştırması  
#### ✅ Cevap 258: Struct eşitliği ve karşılaştırma

Go'da tüm alanları karşılaştırılabilir olan struct'lar doğrudan `==` operatörü ile karşılaştırılabilir. Burada iki `Point` struct'ı karşılaştırılır.

```go
package main
import "fmt"

type Point struct {
    X, Y int
}

func main() {
    p1 := Point{X: 1, Y: 2}
    p2 := Point{X: 1, Y: 2}
    if p1 == p2 {
        fmt.Println("Noktalar eşit")
    } else {
        fmt.Println("Noktalar eşit değil")
    }
}
```
