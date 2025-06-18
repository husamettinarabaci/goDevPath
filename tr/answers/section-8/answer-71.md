## 📘 Bölüm: Structlar  
### 🔹 Kategori: Struct tanımlama ve örnek oluşturma  
#### ✅ Cevap 71: Struct tanımlama ve örnek oluşturma

Go'da struct'lar, ilgili verileri bir arada tutmak için kullanılır. Burada, `Book` struct'ı tanımlanıyor, bir örneği oluşturulup alanlarına değer atanıyor ve struct ekrana yazdırılıyor.

```go
package main
import "fmt"

type Book struct {
    title string
    pages int
}

func main() {
    b := Book{"The Go Programming Language", 380}
    fmt.Println(b)
}
```
