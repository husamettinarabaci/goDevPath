## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Boş Arayüz (`interface{}`) Kullanımı  
#### ✅ Cevap 112: Boş arayüz (`interface{}`) kullanımı

Go'da boş arayüz (`interface{}`), herhangi bir tipteki değeri tutabilir ve bu nedenle jenerik programlama için kullanışlıdır. Tip doğrulama veya `fmt` paketi ile değerin tipi ve değeri çalışma zamanında incelenebilir. İşte bir örnek:

```go
package main
import (
    "fmt"
    "reflect"
)

func degeriYazdir(v interface{}) {
    fmt.Printf("Değer: %v, Tip: %s\n", v, reflect.TypeOf(v))
}

func main() {
    var herhangi interface{}
    herhangi = 42
    degeriYazdir(herhangi)
    herhangi = "merhaba"
    degeriYazdir(herhangi)
    herhangi = struct{ Isim string }{"Go"}
    degeriYazdir(herhangi)
}
```
