## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ile JSON kodlama/çözme  
#### ✅ Cevap 115: Arayüz ile JSON kodlama/çözme

Go'da arayüz değerlerini JSON ile kodlamak ve çözmek için tip bilgisinin kaybolmamasını sağlamak gerekir. Bunun için genellikle özel bir tip alanı kullanılır.

Aşağıda, arayüz değerlerinden oluşan bir slice'ın JSON'a kodlanıp tekrar çözüldüğü bir örnek görebilirsiniz:

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Hayvan interface {
    Ses() string
}

type Kopek struct {
    Tip   string `json:"type"`
    Isim  string `json:"name"`
    Irk   string `json:"breed"`
}

func (k Kopek) Ses() string {
    return "Hav!"
}

type Kedi struct {
    Tip   string `json:"type"`
    Isim  string `json:"name"`
    Renk  string `json:"color"`
}

func (k Kedi) Ses() string {
    return "Miyav!"
}

func main() {
    hayvanlar := []Hayvan{
        Kopek{Tip: "kopek", Isim: "Karabas", Irk: "Golden"},
        Kedi{Tip: "kedi", Isim: "Pamuk", Renk: "Beyaz"},
    }

    // Kodlama: JSON için []interface{}'a çevir
    var ham []interface{}
    for _, h := range hayvanlar {
        ham = append(ham, h)
    }
    data, _ := json.Marshal(ham)
    fmt.Println(string(data))

    // Çözme: tip alanını kullanarak tekrar oluştur
    var cozulmus []map[string]interface{}
    _ = json.Unmarshal(data, &cozulmus)
    for _, item := range cozulmus {
        switch item["type"] {
        case "kopek":
            kopek := Kopek{
                Tip:   item["type"].(string),
                Isim:  item["name"].(string),
                Irk:   item["breed"].(string),
            }
            fmt.Println(kopek.Isim, "diyor ki:", kopek.Ses())
        case "kedi":
            kedi := Kedi{
                Tip:   item["type"].(string),
                Isim:  item["name"].(string),
                Renk:  item["color"].(string),
            }
            fmt.Println(kedi.Isim, "diyor ki:", kedi.Ses())
        }
    }
}
```

Bu örnekte, tip bilgisini korumak için `type` alanı kullanılmış ve JSON'dan çözüldükten sonra orijinal tipler doğru şekilde tekrar oluşturulmuştur.
