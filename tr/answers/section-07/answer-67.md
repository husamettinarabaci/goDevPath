## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: `make` fonksiyonu kullanımı  
#### ✅ Cevap 67: `make` fonksiyonu kullanımı

Go'da `make` fonksiyonu, slice, map ve channel başlatmak için kullanılır. Burada, belirli uzunluk ve kapasiteye sahip bir tamsayı slice'ı oluşturuyor, değer atıyor ve slice ile birlikte uzunluk ve kapasitesini ekrana yazdırıyoruz.

```go
package main
import "fmt"

func main() {
    s := make([]int, 3, 5) // int slice, uzunluk 3, kapasite 5
    s[0] = 10
    s[1] = 20
    s[2] = 30
    fmt.Println(s)         // çıktı: [10 20 30]
    fmt.Println(len(s))    // çıktı: 3
    fmt.Println(cap(s))    // çıktı: 5
}
```
