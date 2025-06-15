## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 103: Metot zincirleme

Go'da metot zincirlemesi, pointer alıcıya sahip metotların struct pointer'ı döndürmesiyle sağlanır. Böylece birden fazla metot tek satırda çağrılabilir. Örnek:

```go
package main
import "fmt"

type Sayac struct {
    Deger int
}

func (s *Sayac) Ekle(n int) *Sayac {
    s.Deger += n
    return s
}

func (s *Sayac) Carp(n int) *Sayac {
    s.Deger *= n
    return s
}

func main() {
    sayac := &Sayac{}
    sayac.Ekle(2).Carp(5)
    fmt.Println(sayac.Deger) // 10
}
```
