## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ile özel hata tipleri  
#### ✅ Cevap 116: Arayüz ile özel hata tipleri

Go'da kendi hata tipinizi tanımlamak için `error` arayüzündeki `Error()` metodunu uygulayabilirsiniz. Böylece hatalara özel alanlar ve mantık ekleyebilirsiniz.

Aşağıda özel hata tipi ve kullanımı örneği yer almaktadır:

```go
package main
import (
    "fmt"
)

type BenimHatam struct {
    Kod    int
    Mesaj  string
}

func (e BenimHatam) Error() string {
    return fmt.Sprintf("Hata %d: %s", e.Kod, e.Mesaj)
}

func riskliIslem(basarisiz bool) error {
    if basarisiz {
        return BenimHatam{Kod: 404, Mesaj: "Kaynak bulunamadı"}
    }
    return nil
}

func main() {
    err := riskliIslem(true)
    if err != nil {
        // Tip doğrulama ile özel hatayı kontrol et
        if benimHata, ok := err.(BenimHatam); ok {
            fmt.Println("Özel hata oluştu:", benimHata)
            fmt.Println("Hata kodu:", benimHata.Kod)
        } else {
            fmt.Println("Diğer hata:", err)
        }
    } else {
        fmt.Println("İşlem başarılı.")
    }
}
```

Bu örnekte, özel hata tipi tanımlanmış, bir fonksiyondan döndürülmüş ve hata yakalanırken tip doğrulama ile alanlarına erişilmiştir.
