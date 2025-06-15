## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 102: Pointer ve değer alıcılar

Go'da metotlar değer veya pointer alıcıya sahip olabilir. Değer alıcı, struct'ın bir kopyasını alır ve değişiklikler orijinali etkilemez. Pointer alıcı ise orijinal struct'ı değiştirebilir. Örnek:

```go
package main
import "fmt"

type Sayac struct {
    Deger int
}

func (s Sayac) DegeriArttirDeger() {
    s.Deger++
}

func (s *Sayac) DegeriArttirPointer() {
    s.Deger++
}

func main() {
    sayac := Sayac{Deger: 1}
    sayac.DegeriArttirDeger()
    fmt.Println("DegeriArttirDeger sonrası:", sayac.Deger) // 1
    sayac.DegeriArttirPointer()
    fmt.Println("DegeriArttirPointer sonrası:", sayac.Deger) // 2
}
```
