## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: If/Else Deyimleri  
#### ✅ Cevap 21: `if`, `else if` ve `else` kullanımı

Go'da `if`, `else if` ve `else` deyimleri, koşullara göre programın akışını kontrol etmek için kullanılır. Örnek:

```go
package main
import "fmt"

func main() {
    var sayi int = -5
    if sayi > 0 {
        fmt.Println("Pozitif sayı")
    } else if sayi == 0 {
        fmt.Println("Sıfır")
    } else {
        fmt.Println("Negatif sayı")
    }
}
```
