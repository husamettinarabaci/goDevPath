## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer Kullanımı, new/make, Struct Pointerları  
#### ✅ Cevap 61: Pointer tanımlama ve kullanma

Go'da pointer, bir değişkenin bellekteki adresini tutar. `*` operatörü ile pointer tanımlanır, `&` ile bir değişkenin adresi alınır. `*` ile pointer çözülerek (dereference) değere erişilir.

```go
package main
import "fmt"

func main() {
    var x int = 10
    var p *int = &x

    fmt.Println("x'in değeri:", x)
    fmt.Println("Pointer ile değer:", *p)
}
```

Bu programda bir tamsayı değişkeni ve ona işaret eden bir pointer tanımlanır, ardından değer hem değişken hem de pointer ile ekrana yazdırılır.
