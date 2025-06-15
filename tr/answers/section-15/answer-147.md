## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 147: Kanal kapatma

Bu örnekte, bir kanalın nasıl kapatılacağı ve `close` fonksiyonu ile "virgül ok" idiomu kullanılarak kanalın kapandığının nasıl tespit edileceği gösterilmiştir. Alıcılar, alma işleminin ikinci değerini kullanarak kanalın kapalı olup olmadığını kontrol edebilir.

```go
package main
import "fmt"

func main() {
    ch := make(chan int)
    go func() {
        for i := 1; i <= 3; i++ {
            ch <- i
        }
        close(ch)
    }()
    for {
        val, ok := <-ch
        if !ok {
            fmt.Println("Kanal kapandı")
            break
        }
        fmt.Println("Alındı:", val)
    }
}
```
