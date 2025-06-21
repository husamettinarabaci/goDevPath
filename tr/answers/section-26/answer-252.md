## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 252: Değer alıcı ile metot oluşturma

Değer alıcı ile tanımlanan metotlar, struct'ın bir kopyası üzerinde çalışır. Burada `Rectangle` struct'ı ve alanı hesaplayan `Area` metodu tanımlanır.

```go
package main
import "fmt"

type Rectangle struct {
    Width, Height float64
}

func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func main() {
    rect := Rectangle{Width: 5, Height: 3}
    fmt.Println("Alan:", rect.Area())
}
```
