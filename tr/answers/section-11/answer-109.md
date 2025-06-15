## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Arayüzlerde Tip Switch Kullanımı  
#### ✅ Cevap 109: Arayüzlerde tip switch kullanımı

Go'da tip switch, bir arayüz değişkeninde tutulan değerin dinamik tipini belirlemenizi ve her tipe göre farklı işlemler yapmanızı sağlar. Aşağıda aynı arayüzü uygulayan iki struct ile örnek verilmiştir:

```go
package main
import "fmt"

type Hayvan interface {
    SesCikar() string
}

type Kopek struct {}
func (k Kopek) SesCikar() string { return "Hav!" }

type Kedi struct {}
func (k Kedi) SesCikar() string { return "Miyav!" }

func tanila(h Hayvan) {
    switch v := h.(type) {
    case Kopek:
        fmt.Println("Bu bir Kopek:", v.SesCikar())
    case Kedi:
        fmt.Println("Bu bir Kedi:", v.SesCikar())
    default:
        fmt.Println("Bilinmeyen hayvan")
    }
}

func main() {
    var h Hayvan
    h = Kopek{}
    tanila(h)
    h = Kedi{}
    tanila(h)
}
```
