## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer Kullanımı, new/make, Struct Pointerları  
#### ✅ Cevap 62: Pointer'ı fonksiyona parametre olarak geçirme

Go'da bir pointer'ı fonksiyona geçirerek, fonksiyonun orijinal değişkeni değiştirmesini sağlayabilirsiniz. Fonksiyon, değişkenin adresini alır ve `*` ile değeri değiştirir.

```go
package main
import "fmt"

func arttir(p *int) {
    *p = *p + 1
}

func main() {
    x := 5
    arttir(&x)
    fmt.Println("Arttırma sonrası x:", x) // Çıktı: 6
}
```

Burada, `arttir` fonksiyonu bir tamsayıya işaret eden pointer alır ve o adresteki değeri artırır. Değişiklik orijinal değişkende görülür.
