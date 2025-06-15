## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 146: Tamponlu ve tamponsuz kanallar

Tamponsuz kanallarda gönderici ve alıcı aynı anda hazır olmalıdır. Tamponlu kanallarda ise kapasite kadar değer, alıcı olmadan gönderilebilir. Bu örnekte her iki davranış da gösterilmiştir.

```go
package main
import "fmt"

func main() {
    // Tamponsuz kanal
    unbuf := make(chan int)
    go func() {
        unbuf <- 1
        fmt.Println("Tamponsuz kanala gönderildi")
    }()
    val := <-unbuf
    fmt.Println("Tamponsuz kanaldan alındı:", val)

    // Tamponlu kanal
    buf := make(chan int, 2)
    buf <- 10
    fmt.Println("Tamponlu kanala ilk gönderildi")
    buf <- 20
    fmt.Println("Tamponlu kanala ikinci gönderildi")
    fmt.Println("Tamponlu kanaldan alındı:", <-buf)
    fmt.Println("Tamponlu kanaldan alındı:", <-buf)
}
```
