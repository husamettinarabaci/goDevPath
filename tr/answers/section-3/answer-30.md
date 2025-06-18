## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Goto Deyimi  
#### ✅ Cevap 30: Go'da `goto` kullanımı

`goto` deyimi, kodunuzda bir etikete atlamanızı sağlar. Bu örnekte döngü 1'den 5'e kadar sayıları yazdırır, ancak sayı 3 olduğunda döngüden çıkarak etikete atlar ve bir mesaj yazdırır.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 5; i++ {
        if i == 3 {
            goto son
        }
        fmt.Println(i)
    }
son:
    fmt.Println("Etikete atlandı!")
}
```
