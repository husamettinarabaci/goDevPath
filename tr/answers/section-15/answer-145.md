## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 145: Kanallarda gönderme ve alma

Bu örnekte, goroutine'ler arasında iletişim için kanalların nasıl kullanılacağı gösterilmektedir. Ana goroutine bir `int` kanalı oluşturur, yeni bir goroutine başlatıp değeri gönderir ve ardından bu değeri alıp ekrana yazdırır.

```go
package main
import (
    "fmt"
)

func main() {
    ch := make(chan int)
    go func() {
        ch <- 42
    }()
    value := <-ch
    fmt.Println(value)
}
```
