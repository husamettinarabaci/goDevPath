## 📘 Bölüm: Standart Kütüphane Temelleri  
### 🔹 Kategori: `strings` paketini kullanma  
#### ✅ Cevap 182: `strings` paketini kullanma

Go'da `strings` paketi, string işlemleri için birçok kullanışlı fonksiyon sunar. İşte bazı yaygın işlemler:

```go
package main
import (
    "fmt"
    "strings"
)

func main() {
    metin := "Go Harika!"
    fmt.Println(strings.Contains(metin, "Harika")) // true
    fmt.Println(strings.ToUpper(metin))             // "GO HARİKA!"
    fmt.Println(strings.ToLower(metin))             // "go harika!"
    kelimeler := strings.Split(metin, " ")
    fmt.Println(kelimeler) // [Go Harika!]
}
```

Bu program, alt string arama, harf dönüşümü ve string'i bölme işlemlerini `strings` paketiyle gösterir.
