## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: error tipi, özel hatalar, panic/recover  
#### ✅ Cevap 139: main fonksiyonunda hata yönetimi

Go'da, `main` fonksiyonunda hata yönetimi genellikle diğer fonksiyonlardan dönen hatanın kontrol edilmesi ve kullanıcıya uygun bir mesaj yazdırılması ile yapılır. Bu, programın beklenmedik şekilde çökmesini önler.

```go
package main
import (
    "errors"
    "fmt"
)

func birSeyYap() error {
    return errors.New("bir şeyler ters gitti")
}

func main() {
    err := birSeyYap()
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    fmt.Println("İşlem başarılı")
}
```
