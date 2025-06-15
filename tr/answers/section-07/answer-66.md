## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: `new` fonksiyonu kullanımı  
#### ✅ Cevap 66: `new` fonksiyonu kullanımı

Go'da `new` fonksiyonu, bir değişken için bellek ayırır ve ona işaretçi döndürür. Burada, `new(int)` ile bir `int` için pointer elde ediyor, pointer üzerinden değer atıyor ve hem değeri hem adresini ekrana yazdırıyoruz.

```go
package main
import "fmt"

func main() {
    p := new(int)      // int için bellek ayır, p'nin tipi *int
    *p = 42            // pointer üzerinden değer ata
    fmt.Println("Değer:", *p)
    fmt.Println("Adres:", p)
}
```
