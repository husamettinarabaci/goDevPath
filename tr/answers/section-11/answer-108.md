## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Arayüzlerde Tip Doğrulama (Type Assertion)  
#### ✅ Cevap 108: Arayüzlerde tip doğrulama (type assertion)

Go'da tip doğrulama (type assertion), bir arayüz değişkeninde tutulan değerin altında yatan somut tipe ulaşmanızı sağlar. `deger, ok := arayuz.(Tip)` sözdizimi ile güvenli şekilde tip kontrolü ve erişimi yapılabilir. İşte bir örnek:

```go
package main
import "fmt"

type Tanitici interface {
    Tanit() string
}

type Kisi struct {
    Isim string
}

func (k Kisi) Tanit() string {
    return "Kişi: " + k.Isim
}

func main() {
    var t Tanitici = Kisi{Isim: "Go Geliştirici"}
    fmt.Println(t.Tanit())

    // Tip doğrulama
    k, ok := t.(Kisi)
    if ok {
        fmt.Println("Tip doğrulama başarılı! İsim:", k.Isim)
    } else {
        fmt.Println("Tip doğrulama başarısız.")
    }
}
```
