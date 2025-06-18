## 📘 Bölüm: Structlar  
### 🔹 Kategori: Struct Karşılaştırma  
#### ✅ Cevap 79: Struct karşılaştırma

Go'da, tüm alanları karşılaştırılabilir (comparable) ise struct'lar doğrudan karşılaştırılabilir. Karşılaştırma, tüm alanların eşit olup olmadığını kontrol eder.

```go
package main
import "fmt"

type Point struct {
    x, y int
}

func main() {
    p1 := Point{x: 1, y: 2}
    p2 := Point{x: 1, y: 2}
    p3 := Point{x: 2, y: 3}
    fmt.Println("p1 == p2:", p1 == p2) // true
    fmt.Println("p1 == p3:", p1 == p3) // false
}
```
