## 📘 Bölüm: Mapler  
### 🔹 Kategori: Map'e Eleman Ekleme ve Silme  
#### ✅ Cevap 92: Map'e eleman ekleme ve silme

Go'da bir map'e yeni bir anahtar atayarak eleman ekleyebilir, `delete` fonksiyonu ile eleman silebilirsiniz. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"elma": 5}
    fmt.Println("İlk map:", m)
    m["muz"] = 3
    fmt.Println("Muz eklendikten sonra:", m)
    delete(m, "elma")
    fmt.Println("Elma silindikten sonra:", m)
}
```

Bu programda map'e eleman ekleme ve silme işlemleri gösterilmiş, her işlem sonrası map yazdırılmıştır.
