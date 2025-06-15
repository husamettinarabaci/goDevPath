## 📘 Bölüm: Standart Kütüphane Temelleri  
### 🔹 Kategori: `strconv` paketini kullanma  
#### ✅ Cevap 183: `strconv` paketini kullanma

Go'da `strconv` paketi, string ve sayılar arasında dönüşüm için fonksiyonlar sunar.

Örnek:

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    // String'den int'e
    s := "42"
    i, err := strconv.Atoi(s)
    if err != nil {
        fmt.Println("Dönüşüm hatası:", err)
    } else {
        fmt.Println("String'den int'e:", i)
    }

    // Int'ten string'e
    n := 123
    str := strconv.Itoa(n)
    fmt.Println("Int'ten string'e:", str)

    // Float'tan string'e (hassasiyetli)
    f := 3.14159
    fstr := strconv.FormatFloat(f, 'f', 2, 64)
    fmt.Println("Float'tan string'e (2 basamak):", fstr)
}
```

Bu program, `strconv` paketiyle string ve sayılar arasında dönüşümü gösterir.
