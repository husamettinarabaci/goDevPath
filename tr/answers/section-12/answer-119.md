## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ve yansıma (reflection)  
#### ✅ Cevap 119: Arayüz ve yansıma (reflection)

Go'da `reflect` paketi, arayüz değişkenlerinin tipini ve değerini çalışma zamanında incelemenizi sağlar. Bu, dinamik tip analizi ve ileri düzey programlama teknikleri için kullanışlıdır.

Aşağıda bir örnek görebilirsiniz:

```go
package main
import (
    "fmt"
    "reflect"
)

type Hayvan interface {
    Ses() string
}

type Kopek struct {
    Isim string
}

func (k Kopek) Ses() string {
    return "Hav!"
}

func main() {
    var h Hayvan = Kopek{Isim: "Karabas"}
    fmt.Println("Dinamik tip:", reflect.TypeOf(h))
    fmt.Println("Dinamik değer:", reflect.ValueOf(h))

    // Yansıma ile alttaki struct alanlarına erişim
    v := reflect.ValueOf(h)
    if v.Kind() == reflect.Struct {
        for i := 0; i < v.NumField(); i++ {
            fmt.Printf("Alan %d: %v\n", i, v.Field(i))
        }
    } else if v.Kind() == reflect.Interface {
        elem := v.Elem()
        for i := 0; i < elem.NumField(); i++ {
            fmt.Printf("Alan %d: %v\n", i, elem.Field(i))
        }
    }
}
```

Bu örnekte, `reflect.TypeOf` ve `reflect.ValueOf` ile arayüzün dinamik tipi ve değeri incelenmiş, ayrıca yansıma ile struct alanlarına erişim gösterilmiştir.
