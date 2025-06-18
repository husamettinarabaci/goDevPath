## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer Kullanımı, new/make, Struct Pointerları  
#### ✅ Cevap 64: Nil pointer ve sıfır değerler

Go'da başlatılmamış bir pointer'ın değeri sıfır değer olan `nil`'dir. Bir pointer'ı çözümlemeden önce nil olup olmadığını kontrol etmek gerekir, aksi halde çalışma zamanı hatası (panic) oluşur.

```go
package main
import "fmt"

func main() {
    var p *int // nil pointer
    fmt.Println("Pointer değeri:", p) // Çıktı: <nil>

    if p != nil {
        fmt.Println(*p)
    } else {
        fmt.Println("Pointer nil, çözümleme yapılamaz.")
    }
}
```

Nil bir pointer'ı çözümlemek çalışma zamanı hatasına yol açar. Bu yüzden pointer'lar kullanılmadan önce nil kontrolü yapılmalıdır.
