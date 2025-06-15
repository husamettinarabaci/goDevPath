## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine, WaitGroup, kanal kullanımı  
#### ✅ Cevap 144: İletişim için kanal kullanımı

Kanallar, goroutine'ler arasında güvenli iletişim sağlar. Bir goroutine'den bir değer gönderip diğerinde alabilirsiniz.

```go
package main
import "fmt"

func degerGonder(ch chan int) {
    ch <- 42
}

func main() {
    ch := make(chan int)
    go degerGonder(ch)
    deger := <-ch
    fmt.Println("Alındı:", deger)
}
```
