## 📘 Bölüm: Kontrol Akışı  
### 🔹 Kategori: For Döngüleri  
#### ✅ Cevap 24: `for` ile while döngüsü gibi kullanım

Go'da, başlatma ve artış ifadeleri olmadan `for` döngüsü while döngüsü gibi kullanılabilir. Örnek:

```go
package main
import "fmt"

func main() {
    i := 1
    for i <= 5 {
        fmt.Println(i)
        i++
    }
}
```
