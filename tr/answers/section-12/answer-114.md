## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz ve map kullanımı  
#### ✅ Cevap 114: Arayüz ve map kullanımı

Go'da map değerlerinde arayüz tipi kullanmak, farklı struct tiplerini tek bir map'te saklamamıza olanak tanır. Ancak, arayüzler map anahtarı olarak kullanılacaksa, alttaki tipin karşılaştırılabilir olması gerekir. En yaygın kullanım, arayüzün map değeri olarak kullanılmasıdır.

Aşağıda, arayüzün map değeri olarak kullanıldığı bir örnek görebilirsiniz:

```go
package main
import "fmt"

// Arayüz tanımı
type Sekil interface {
    Alan() float64
}

type Daire struct {
    YariCap float64
}

func (d Daire) Alan() float64 {
    return 3.14 * d.YariCap * d.YariCap
}

type Kare struct {
    Kenar float64
}

func (k Kare) Alan() float64 {
    return k.Kenar * k.Kenar
}

func main() {
    // Anahtarları string, değerleri Sekil arayüzü olan bir map
    sekiller := make(map[string]Sekil)
    sekiller["daire"] = Daire{YariCap: 2}
    sekiller["kare"] = Kare{Kenar: 3}

    for isim, sekil := range sekiller {
        fmt.Printf("%s alanı: %.2f\n", isim, sekil.Alan())
    }
}
```

Bu örnekte, Sekil arayüzünü uygulayan farklı struct'lar tek bir map'te saklanmış ve arayüz metodu çağrılarak sonuçlar ekrana yazdırılmıştır.
