## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 52: İç içe fonksiyon çağrıları

Go'da fonksiyonlar başka fonksiyonları çağırabilir ve onların dönüş değerlerini kullanabilir. Burada, `outer` fonksiyonu `inner` fonksiyonunu çağırır ve dönen string'i ekrana yazdırır.

```go
package main
import "fmt"

func inner() string {
    return "İçeriden merhaba!"
}

func outer() {
    sonuc := inner()
    fmt.Println(sonuc)
}

func main() {
    outer()
}
```
