## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer Kullanımı, new/make, Struct Pointerları  
#### ✅ Cevap 63: Fonksiyondan pointer döndürme

Go'da bir fonksiyondan yerel bir değişkenin adresini döndürebilirsiniz. Go'nun bellek yönetimi, bu değişkenin pointer ile kullanılmasını güvenli kılar.

```go
package main
import "fmt"

func yeniInt() *int {
    x := 42
    return &x
}

func main() {
    p := yeniInt()
    fmt.Println("Pointer ile değer:", *p) // Çıktı: 42
}
```

Burada, `yeniInt` fonksiyonu yerel bir değişkenin adresini döndürür ve bu değer `main` fonksiyonunda pointer ile kullanılır.
