## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Döngüler ve Akış Kontrolü  
#### ✅ Cevap 26: `continue` ile döngü adımını atlama

`continue` ifadesi, döngüde mevcut yinelemeyi atlayıp bir sonraki adıma geçmek için kullanılır. Bu örnekte döngü 1'den 10'a kadar sayıları yazdırır, ancak 5 sayısını atlar.

```go
package main
import "fmt"

func main() {
    for i := 1; i <= 10; i++ {
        if i == 5 {
            continue
        }
        fmt.Println(i)
    }
}
```
