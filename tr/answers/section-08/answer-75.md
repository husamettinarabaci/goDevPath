## 📘 Bölüm: Structlar  
### 🔹 Kategori: İsimsiz Structlar  
#### ✅ Cevap 75: İsimsiz structlar

Go'da isimsiz struct'lar, hızlı ve tek seferlik veri yapıları için kullanışlıdır. Doğrudan tanımlanıp başlatılabilirler.

```go
package main
import "fmt"

func main() {
    kitap := struct {
        title string
        pages int
    }{
        title: "Go Programlama",
        pages: 350,
    }
    fmt.Println("Başlık:", kitap.title)
    fmt.Println("Sayfa:", kitap.pages)
}
```
