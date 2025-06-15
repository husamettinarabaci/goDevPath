## 📘 Bölüm: Structlar  
### 🔹 Kategori: Struct alanlarına erişim  
#### ✅ Cevap 72: Struct alanlarına erişim

Go'da struct alanlarına nokta (`.`) notasyonu ile erişilir. Burada, `Book` struct'ı tanımlanıyor, bir örneği oluşturuluyor ve her alan ayrı ayrı ekrana yazdırılıyor.

```go
package main
import "fmt"

type Book struct {
    title string
    pages int
}

func main() {
    b := Book{"Go in Action", 300}
    fmt.Println(b.title)
    fmt.Println(b.pages)
}
```
