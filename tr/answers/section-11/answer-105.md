## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Arayüzler  
#### ✅ Cevap 105: Basit bir arayüz tanımlama

Go'da arayüz, bir dizi metot imzası tanımlar. Bu metotları uygulayan her tip, o arayüzü karşılar. Örnek:

```go
package main
import "fmt"

type Selamlayici interface {
    Selamla()
}

type Kisi struct {
    Isim string
}

func (k Kisi) Selamla() {
    fmt.Println("Merhaba, benim adım", k.Isim)
}

func SelamVer(s Selamlayici) {
    s.Selamla()
}

func main() {
    k := Kisi{Isim: "Ayşe"}
    SelamVer(k)
}
```
