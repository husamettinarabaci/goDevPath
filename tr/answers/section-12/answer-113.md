## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ve Slice Kullanımı  
#### ✅ Cevap 113: Arayüz ve slice kullanımı

Go'da arayüz tipinde bir slice, arayüzü uygulayan herhangi bir tipteki değerleri tutabilir. Bu sayede farklı tipleri tek bir koleksiyonda saklayıp kullanabilirsiniz. İşte bir örnek:

```go
package main
import "fmt"

type Konusan interface {
    Konus() string
}

type Kopek struct {}
func (k Kopek) Konus() string { return "Hav!" }

type Kedi struct {}
func (k Kedi) Konus() string { return "Miyav!" }

func main() {
    var hayvanlar []Konusan
    hayvanlar = append(hayvanlar, Kopek{}, Kedi{})
    for _, h := range hayvanlar {
        fmt.Println(h.Konus())
    }
}
```
