## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: Döngüler ve Akış Kontrolü  
#### ✅ Cevap 27: `break` ve `continue` ile etiket kullanımı

Etiketler, iç içe döngülerde `break` ve `continue` ifadeleriyle akışı kontrol etmek için kullanılabilir. Bu örnekte, `i == 2` ve `j == 3` olduğunda her iki döngüden de çıkılır, `j == 1` olduğunda ise dış döngüye devam edilir.

```go
package main
import "fmt"

func main() {
outer:
    for i := 1; i <= 3; i++ {
        for j := 1; j <= 3; j++ {
            if i == 2 && j == 3 {
                break outer
            }
            if j == 1 {
                continue outer
            }
            fmt.Printf("i = %d, j = %d\n", i, j)
        }
    }
}
```
