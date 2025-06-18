## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Döngüler ve Akış Kontrolü  
#### ✅ Cevap 25: `break` ile döngüden çıkma

`break` ifadesi, bir döngü tüm yinelemeleri tamamlamadan çıkmak için kullanılır. Bu örnekte döngü 1'den 10'a kadar sayıları yazdırır, ancak sayı 5 olduğunda döngüden çıkar.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 10; i++ {
        fmt.Println(i)
        if i == 5 {
            break
        }
    }
}
```
