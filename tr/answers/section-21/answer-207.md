## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Özel Koleksiyon Tipleri Yazma  
#### ✅ Cevap 207: Özel koleksiyon tipleri yazma

Go'da struct ve metotlar kullanarak kendi koleksiyon tiplerinizi tanımlayabilirsiniz. Aşağıda basit bir yığın (stack) örneği verilmiştir:

```go
package main
import "fmt"

type Yigin struct {
    elemanlar []int
}

func (y *Yigin) Ekle(eleman int) {
    y.elemanlar = append(y.elemanlar, eleman)
}

func (y *Yigin) Cikar() int {
    if len(y.elemanlar) == 0 {
        panic("yığın boş")
    }
    eleman := y.elemanlar[len(y.elemanlar)-1]
    y.elemanlar = y.elemanlar[:len(y.elemanlar)-1]
    return eleman
}

func (y *Yigin) Bak() int {
    if len(y.elemanlar) == 0 {
        panic("yığın boş")
    }
    return y.elemanlar[len(y.elemanlar)-1]
}

func main() {
    var y Yigin
    y.Ekle(10)
    y.Ekle(20)
    fmt.Println(y.Bak()) // 20
    fmt.Println(y.Cikar()) // 20
    fmt.Println(y.Cikar()) // 10
}
```
