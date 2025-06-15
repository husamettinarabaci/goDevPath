## 📘 Bölüm: Metotlar ve Arayüzler II  
### 🔹 Kategori: Arayüz değerlerini karşılaştırma  
#### ✅ Cevap 118: Arayüz değerlerini karşılaştırma

Go'da arayüz değerleri, dinamik tipleri ve dinamik değerleri aynıysa eşit kabul edilir. Alttaki tipler farklıysa karşılaştırma false döner. Her ikisi de nil ise karşılaştırma true olur.

Aşağıda bir örnek görebilirsiniz:

```go
package main
import "fmt"

type Sekil interface {
    Alan() float64
}

type Daire struct {
    Y float64
}

func (d Daire) Alan() float64 {
    return 3.14 * d.Y * d.Y
}

type Kare struct {
    K float64
}

func (k Kare) Alan() float64 {
    return k.K * k.K
}

func main() {
    var a, b Sekil
    a = Daire{Y: 2}
    b = Daire{Y: 2}
    fmt.Println("a == b:", a == b) // true, aynı tip ve değer

    b = Daire{Y: 3}
    fmt.Println("a == b:", a == b) // false, farklı değer

    b = Kare{K: 2}
    fmt.Println("a == b:", a == b) // false, farklı tip

    var c Sekil
    var d Sekil
    fmt.Println("c == d:", c == d) // true, ikisi de nil
}
```

Bu örnekte, Go'da arayüz değerlerinin karşılaştırılması, farklı tipler, değerler ve nil arayüzler için gösterilmiştir.
