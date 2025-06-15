## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Parametreler  
#### ✅ Cevap 50: Pointer parametreli fonksiyon

Bir değişkenin değerini fonksiyon içinde değiştirmek için, o değişkenin pointer'ını parametre olarak geçebilirsiniz. Fonksiyon, pointer'ı çözümleyerek (dereference) ilgili değeri değiştirebilir.

```go
package main
import "fmt"

func arttir(sayi *int) {
    *sayi = *sayi + 1
}

func main() {
    x := 10
    arttir(&x)
    fmt.Println(x) // Çıktı: 11
}
```
