## 📘 Bölüm: Structlar  
### 🔹 Kategori: Pointer Alanlı Structlar  
#### ✅ Cevap 76: Pointer alanlı structlar

Go'da struct'lar pointer alanlara sahip olabilir. Bu, veriye kopyalamadan referans vermek veya paylaşmak için kullanışlıdır.

```go
package main
import "fmt"

type Book struct {
    title  string
    author *string
}

func main() {
    yazar := "John Doe"
    b := Book{
        title:  "Go ile Uygulama",
        author: &yazar,
    }
    fmt.Println("Başlık:", b.title)
    fmt.Println("Yazar:", *b.author)
}
```
