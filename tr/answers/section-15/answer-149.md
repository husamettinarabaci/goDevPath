## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 149: Temel select deyimi

Bu örnekte, birden fazla kanaldan veri almak için `select` deyiminin nasıl kullanılacağı gösterilmiştir. Program, iki farklı kanala kısa bir gecikmeden sonra değer gönderen iki goroutine başlatır ve ana fonksiyon, hazır olan kanaldan değeri alır.

```go
package main
import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan int)
    ch2 := make(chan int)
    go func() {
        time.Sleep(100 * time.Millisecond)
        ch1 <- 1
    }()
    go func() {
        time.Sleep(200 * time.Millisecond)
        ch2 <- 2
    }()
    for i := 0; i < 2; i++ {
        select {
        case v := <-ch1:
            fmt.Println("ch1'dan alındı:", v)
        case v := <-ch2:
            fmt.Println("ch2'den alındı:", v)
        }
    }
}
```
