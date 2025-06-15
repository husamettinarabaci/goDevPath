## 📘 Bölüm: Mapler  
### 🔹 Kategori: Map Üzerinde Yineleme  
#### ✅ Cevap 94: Map üzerinde yineleme

Go'da bir map üzerinde `range` ile `for` döngüsü kullanarak yineleme yapılabilir. Bu şekilde her anahtar ve değere erişebilirsiniz. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"elma": 5, "muz": 3}
    for key, value := range m {
        fmt.Printf("Anahtar: %s, Değer: %d\n", key, value)
    }
}
```

Bu programda map'in tüm anahtar ve değerleri `for` ve `range` ile yazdırılmıştır.
