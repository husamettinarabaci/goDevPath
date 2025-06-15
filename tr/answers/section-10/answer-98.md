## 📘 Bölüm: Mapler  
### 🔹 Kategori: Map İşlemleri  
#### ✅ Cevap 98: Map'ten eleman silme

Go'da bir map'ten eleman silmek için yerleşik `delete` fonksiyonu kullanılır. Bu fonksiyon, map ve silinecek anahtarı alır. Anahtar yoksa, `delete` hiçbir şey yapmaz. İşte bir örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"a": 1, "b": 2, "c": 3}
    fmt.Println("Silme öncesi:", m)
    delete(m, "b")
    fmt.Println("'b' silindikten sonra:", m)
    delete(m, "x") // Olmayan bir anahtarı silmek güvenlidir
    fmt.Println("'x' silinmeye çalışıldıktan sonra:", m)
}
```
