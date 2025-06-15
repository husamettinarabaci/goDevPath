## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz bileşimi  
#### ✅ Cevap 117: Arayüz bileşimi

Go'da arayüz bileşimi, birden fazla arayüzü yeni bir arayüzde gömerek daha karmaşık arayüzler oluşturmayı sağlar. Tüm gömülü metodları uygulayan bir struct, bileşik arayüzü karşılar.

Aşağıda bir örnek görebilirsiniz:

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

func main() {
    var oy OkuyucuYazici = &Dosya{}
    oy.Yaz("Merhaba, Go!")
    fmt.Println(oy.Oku())
}
```

Burada, `OkuyucuYazici` arayüzü, `Okuyucu` ve `Yazici` arayüzlerini gömüyor. `Dosya` struct'ı her iki arayüzü de uyguladığı için bileşik arayüzü karşılar.
