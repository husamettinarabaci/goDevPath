## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 169: Dizin ağacında gezinme

Bu program, Go'da bir dizin ağacında özyinelemeli olarak nasıl gezileceğini gösterir. `filepath.Walk` fonksiyonu ile geçerli dizinden başlayarak her dosya ve dizin ziyaret edilir, yolları yazdırılır ve hatalar uygun şekilde yönetilir.

```go
package main
import (
    "fmt"
    "os"
    "path/filepath"
)

func main() {
    err := filepath.Walk(".", func(path string, info os.FileInfo, err error) error {
        if err != nil {
            fmt.Println("Hata:", err)
            return err
        }
        fmt.Println(path)
        return nil
    })
    if err != nil {
        fmt.Println("Yürütme hatası:", err)
    }
}
```
