## 📘 Bölüm: Mapler  
### 🔹 Kategori: Slice Değerli Mapler  
#### ✅ Cevap 97: Slice değerli mapler

Go'da slice'lar map değerleri olarak kullanılabilir. Bu, bir anahtara birden fazla değer atamak için kullanışlıdır. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string][]int{
        "çiftler": {2, 4, 6},
        "tekler":  {1, 3, 5},
    }
    fmt.Println(m)
    for anahtar, degerler := range m {
        fmt.Printf("%s: %v\n", anahtar, degerler)
    }
}
```

Bu programda slice değerli bir map oluşturulmuş ve içeriği yazdırılmıştır.
