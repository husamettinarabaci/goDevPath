## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: error tipi, özel hatalar, panic/recover  
#### ✅ Cevap 137: Hataları yok sayma (boş tanımlayıcı)

Go'da, ihtiyaç duymadığınız değerleri (örneğin hata) yok saymak için boş tanımlayıcı (`_`) kullanabilirsiniz. Bu, hatanın güvenle göz ardı edilebileceğinden emin olduğunuzda kullanılabilir, ancak dikkatli olunmalıdır.

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    value, _ := strconv.Atoi("123") // Hata yok sayılıyor
    fmt.Println(value) // Çıktı: 123
}
```
