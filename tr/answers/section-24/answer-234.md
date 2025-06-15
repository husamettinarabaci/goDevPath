## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar
### 🔹 Kategori: Go'da factory kalıbı
#### ✅ Cevap 234: Go'da factory kalıbı

Factory kalıbı, nesneleri tam tipini belirtmeden oluşturmayı sağlar. Go'da bu genellikle, farklı tipleri döndüren ve ortak bir arayüzü uygulayan bir fonksiyon ile yapılır.

```go
package main
import "fmt"

type Hayvan interface {
    SesCikar() string
}

type Kopek struct{}
func (k Kopek) SesCikar() string { return "Hav!" }

type Kedi struct{}
func (k Kedi) SesCikar() string { return "Miyav!" }

func HayvanFabrikasi(tur string) Hayvan {
    switch tur {
    case "kopek":
        return Kopek{}
    case "kedi":
        return Kedi{}
    default:
        return nil
    }
}

func main() {
    hayvanlar := []string{"kopek", "kedi"}
    for _, tur := range hayvanlar {
        h := HayvanFabrikasi(tur)
        if h != nil {
            fmt.Println(h.SesCikar())
        }
    }
}
```

Bu kalıp, farklı davranışlara sahip nesneleri ortak bir arayüz üzerinden oluşturmanıza olanak tanır.
