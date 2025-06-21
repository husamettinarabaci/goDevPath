## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Arayüzler ve Çok Biçimlilik  
#### ✅ Cevap 270: Arayüzlerle çok biçimlilik sağlama

Go'da arayüzler, farklı tiplerin aynı davranışı sergilemesini sağlar. Burada hem `Circle` hem de `Rectangle` struct'ları `Shape` arayüzünü uygular ve çok biçimlilik sağlanır.

```go
package main
import (
    "fmt"
    "math"
)

type Shape interface {
    Area() float64
}

type Circle struct {
    Radius float64
}

type Rectangle struct {
    Width, Height float64
}

func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func alanYazdir(s Shape) {
    fmt.Printf("Alan: %.2f\n", s.Area())
}

func main() {
    c := Circle{Radius: 2.5}
    r := Rectangle{Width: 4, Height: 3}
    alanYazdir(c)
    alanYazdir(r)
}
```
