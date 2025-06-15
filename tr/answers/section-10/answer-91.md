## 📘 Bölüm: Mapler  
### 🔹 Kategori: Map Tanımlama ve Başlatma  
#### ✅ Cevap 91: Map tanımlama ve başlatma

Go'da map'ler anahtarları değerlerle ilişkilendiren referans tipleridir. `map` anahtar kelimesiyle tanımlanır ve bileşik literal veya `make` fonksiyonu ile başlatılabilir. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"elma": 5, "muz": 3}
    fmt.Println(m)
}
```

Bu örnekte anahtarları string, değerleri int olan bir map oluşturulmuş, iki çift ile başlatılmış ve map terminale yazdırılmıştır.
