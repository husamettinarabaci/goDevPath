## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Switch Deyimleri  
#### ✅ Cevap 28: Birden fazla durumlu `switch` kullanımı

Bir `switch` deyiminde birden fazla durumu tek bir case bloğunda gruplayabilirsiniz. Bu, aynı kodun birden fazla değer için çalışmasını sağlar.

```go
package main
import "fmt"

func main() {
    num := 2
    switch num {
    case 1, 2, 3:
        fmt.Println("num 1, 2 veya 3")
    case 4, 5:
        fmt.Println("num 4 veya 5")
    default:
        fmt.Println("num başka bir şey")
    }
}
```
