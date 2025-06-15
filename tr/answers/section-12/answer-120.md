## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ve dinamik tipler  
#### ✅ Cevap 120: Arayüz ve dinamik tipler

Go'da tip switch, bir arayüz değerinin çalışma zamanındaki dinamik tipini belirlemenizi ve her tipe göre farklı işlemler yapmanızı sağlar.

Aşağıda bir örnek görebilirsiniz:

```go
package main
import "fmt"

type Hayvan interface {
    Ses() string
}

type Kopek struct {
    Isim string
}

func (k Kopek) Ses() string {
    return "Hav!"
}

type Kedi struct {
    Isim string
}

func (k Kedi) Ses() string {
    return "Miyav!"
}

func acikla(h Hayvan) {
    switch v := h.(type) {
    case Kopek:
        fmt.Println("Bu bir Kopek, adı:", v.Isim)
    case Kedi:
        fmt.Println("Bu bir Kedi, adı:", v.Isim)
    default:
        fmt.Println("Bilinmeyen hayvan")
    }
}

func main() {
    acikla(Kopek{Isim: "Karabas"})
    acikla(Kedi{Isim: "Pamuk"})
}
```

Bu örnekte, tip switch ile arayüzde saklanan farklı dinamik tipler yönetilmiş ve her tipe göre farklı mesajlar yazdırılmıştır.
