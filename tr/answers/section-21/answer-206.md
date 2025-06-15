## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Generics Kullanımı  
#### ✅ Cevap 206: Generics kullanımı (Go 1.18+)

Go'da generics (1.18 ve sonrası) ile fonksiyonlar ve tipler herhangi bir tip ile çalışabilir. Aşağıda, bir slice'ın ilk elemanını döndüren generics fonksiyon örneği verilmiştir:

```go
package main
import "fmt"

func Ilk[T any](s []T) T {
    return s[0]
}

func main() {
    tamsayilar := []int{1, 2, 3}
    kelimeler := []string{"a", "b", "c"}
    fmt.Println(Ilk(tamsayilar))   // Çıktı: 1
    fmt.Println(Ilk(kelimeler))    // Çıktı: a
}
```
