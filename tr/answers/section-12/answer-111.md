## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz Gömme  
#### ✅ Cevap 111: Arayüz gömme

Go'da bir arayüzü başka bir arayüzde gömerek daha karmaşık soyutlamalar oluşturabilirsiniz. Gömülü arayüzdeki tüm metodları uygulayan bir struct, yeni arayüzü de karşılamış olur. İşte bir örnek:

```go
package main
import "fmt"

type Okuyucu interface {
    Oku() string
}

type Yazici interface {
    Yaz(s string)
}

type OkuyucuYazici interface {
    Okuyucu
    Yazici
}

type Dosya struct {
    icerik string
}

func (d *Dosya) Oku() string {
    return d.icerik
}

func (d *Dosya) Yaz(s string) {
    d.icerik = s
}

func kullan(oy OkuyucuYazici) {
    oy.Yaz("Merhaba, Go!")
    fmt.Println(oy.Oku())
}

func main() {
    d := &Dosya{}
    kullan(d)
}
```
