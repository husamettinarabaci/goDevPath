## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 53: İsimsiz fonksiyonlara giriş

Go'da isimsiz fonksiyonlar, adı olmayan fonksiyonlardır. Tanımlanıp hemen çağrılabilirler. Aşağıda, isimsiz fonksiyon ile mesaj yazdıran bir örnek verilmiştir.

```go
package main
import "fmt"

func main() {
    func() {
        fmt.Println("Bir isimsiz fonksiyondan merhaba!")
    }()
}
```
