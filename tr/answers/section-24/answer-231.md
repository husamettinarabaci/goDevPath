## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar
### 🔹 Kategori: Hata yönetimi idiomları
#### ✅ Cevap 231: Hata yönetimi idiomları

Go'da hata yönetiminin idiomatik yolu, hataları fonksiyonlardan son dönüş değeri olarak döndürmek ve açıkça kontrol etmektir. Hataları bağlamla sarmalamak hata ayıklamayı kolaylaştırır.

```go
package main
import (
    "errors"
    "fmt"
)

func birSeyYap(flag bool) error {
    if !flag {
        return errors.New("bir şeyler ters gitti")
    }
    return nil
}

func main() {
    err := birSeyYap(false)
    if err != nil {
        // Hata bağlamla sarmalanıyor
        err = fmt.Errorf("birSeyYap başarısız: %w", err)
        fmt.Println(err)
    }
}
```

Bu kalıp, hata yönetimini açık ve izlenebilir kılar; bu da Go'nun temel idiomlarından biridir.
