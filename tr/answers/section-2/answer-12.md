## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Değişken Tanımlama ve Başlatma  
#### ✅ Cevap 12: Birden fazla değişkeni aynı anda tanımlama

Go'da birden fazla değişkeni tek bir satırda tanımlayıp başlatabilirsiniz. Aşağıda bir örnek yer almaktadır:

```go
package main
import "fmt"
func main() {
    var x, y int = 10, 20
    var isim, yas = "Mehmet", 28
    fmt.Println("x:", x, "y:", y)
    fmt.Println("İsim:", isim, "Yaş:", yas)
}
```

Bu program, aynı ve farklı tipte birden fazla değişkenin tek satırda tanımlanıp başlatılmasını ve değerlerinin yazdırılmasını göstermektedir.
