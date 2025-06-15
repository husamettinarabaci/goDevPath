## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 54: Fonksiyon döndüren fonksiyon

Go'da fonksiyonlar başka fonksiyonlar döndürebilir. Bu, closure veya yapılandırılabilir davranışlar oluşturmak için kullanışlıdır. Burada, `makeGreeter` fonksiyonu bir selamlama mesajı yazdıran bir fonksiyon döndürür.

```go
package main
import "fmt"

func makeGreeter() func() {
    return func() {
        fmt.Println("Selamlar, greeter'dan merhaba!")
    }
}

func main() {
    selamla := makeGreeter()
    selamla()
}
```
