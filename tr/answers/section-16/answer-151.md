## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Kanal Yönleri ve Senkronizasyon  
#### ✅ Cevap 151: Kanal yönleri (sadece gönderme, sadece alma)

Bu örnekte, fonksiyonların sadece gönderme veya sadece alma işlemi yapabilmesi için kanal yönü tiplerinin nasıl kullanılacağı gösterilmiştir. `chan<- int` sadece gönderme, `<-chan int` ise sadece alma için kullanılır.

```go
package main
import "fmt"

func gonder(ch chan<- int) {
    ch <- 42
}

func al(ch <-chan int) {
    val := <-ch
    fmt.Println("Alındı:", val)
}

func main() {
    ch := make(chan int)
    go gonder(ch)
    go al(ch)
    // Goroutine'lerin bitmesini beklemek için (örnek amaçlı select)
    // Gerçek uygulamada sync.WaitGroup kullanılmalıdır
    select {}
}
```
