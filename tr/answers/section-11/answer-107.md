## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Arayüz Kullanımı  
#### ✅ Cevap 107: Arayüz değerlerini kullanma

Go'da arayüz değerleri, arayüzü uygulayan herhangi bir değeri tutabilir. Bu sayede farklı tiplerle esnek ve çok biçimli (polymorphic) kod yazabilirsiniz. Burada iki struct aynı arayüzü uygular ve bir fonksiyon arayüz tipini parametre olarak alır.

```go
package main
import "fmt"

// Arayüzü tanımla
type Konusan interface {
    Konus() string
}

// Arayüzü uygulayan ilk struct
type Kopek struct {}
func (k Kopek) Konus() string {
    return "Hav!"
}

// Arayüzü uygulayan ikinci struct
type Kedi struct {}
func (k Kedi) Konus() string {
    return "Miyav!"
}

// Arayüz tipini parametre alan fonksiyon
def konustur(kon Konusan) {
    fmt.Println(kon.Konus())
}

func main() {
    var kon Konusan
    kon = Kopek{}
    konustur(kon)
    kon = Kedi{}
    konustur(kon)
}
```
