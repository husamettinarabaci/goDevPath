## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Switch Deyimi  
#### ✅ Cevap 22: `switch` deyimi kullanımı

Go'da `switch` deyimi, bir değişkenin değerine göre farklı kod bloklarının çalıştırılmasını sağlar. Örnek:

```go
package main
import "fmt"

func main() {
    var sayi int = 2
    switch sayi {
    case 1:
        fmt.Println("Bir")
    case 2:
        fmt.Println("İki")
    case 3:
        fmt.Println("Üç")
    default:
        fmt.Println("Diğer değer")
    }
}
```
