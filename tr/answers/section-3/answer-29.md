## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Switch Deyimleri  
#### ✅ Cevap 29: `switch` deyiminde `fallthrough` kullanımı

Bir `switch` bloğunda `fallthrough` ifadesi, bir sonraki case bloğunun koşulu sağlanmasa bile çalışmasını sağlar.

```go
package main
import "fmt"

func main() {
    num := 1
    switch num {
    case 1:
        fmt.Println("Case 1")
        fallthrough
    case 2:
        fmt.Println("Case 2")
    default:
        fmt.Println("Varsayılan case")
    }
}
```
