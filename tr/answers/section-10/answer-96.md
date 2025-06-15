## 📘 Bölüm: Mapler  
### 🔹 Kategori: Struct Değerli Mapler  
#### ✅ Cevap 96: Struct değerli mapler

Go'da struct'lar map değerleri olarak kullanılabilir. Bu, ilişkili verileri gruplamak için faydalıdır. Örnek:

```go
package main
import "fmt"

type Urun struct {
    Fiyat float64
    Stok  int
}

func main() {
    urunler := map[string]Urun{
        "elma":  {Fiyat: 1.2, Stok: 10},
        "muz":   {Fiyat: 0.8, Stok: 20},
    }
    fmt.Println(urunler)
    for isim, bilgi := range urunler {
        fmt.Printf("%s: Fiyat=%.2f, Stok=%d\n", isim, bilgi.Fiyat, bilgi.Stok)
    }
}
```

Bu programda bir struct tanımlanmış, map değeri olarak kullanılmış ve map'in içeriği yazdırılmıştır.
