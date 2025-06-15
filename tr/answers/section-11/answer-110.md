## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Nil Arayüzler ve Sıfır Değerler  
#### ✅ Cevap 110: Nil arayüzler ve sıfır değerler

Go'da bir arayüzün sıfır değeri `nil`'dir. Yani, bir arayüz değişkenine değer atanmamışsa bu değişken `nil` olur. Bunu basit bir karşılaştırma ile kontrol edebilirsiniz. İşte bir örnek:

```go
package main
import "fmt"

type Tanimlayici interface {
    Tanimla() string
}

func nilMi(i Tanimlayici) {
    if i == nil {
        fmt.Println("Arayüz nil!")
    } else {
        fmt.Println("Arayüz nil değil.")
    }
}

func main() {
    var t Tanimlayici // sıfır değeri nil
    nilMi(t)

    t = nil // açıkça nil atanıyor
    nilMi(t)

    t = struct{Tanimlayici}{ } // nil olmayan değer
    nilMi(t)
}
```
