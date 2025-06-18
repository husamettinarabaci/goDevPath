## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 51: Fonksiyon kapsamı ve değişken ömrü

Go'da bir fonksiyon içinde tanımlanan değişkenler sadece o fonksiyon içinde erişilebilir. Ömürleri fonksiyonun çalışmasıyla sınırlıdır. Dışarıdan erişmeye çalışmak derleme hatasına yol açar.

```go
package main
import "fmt"

func kapsamGoster() {
    x := 42
    fmt.Println(x) // Tamam: x burada erişilebilir
}

func main() {
    kapsamGoster()
    // fmt.Println(x) // HATA: x bu kapsamda tanımlı değil
}
```
