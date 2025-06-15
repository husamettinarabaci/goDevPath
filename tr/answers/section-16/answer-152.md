## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Kanal Yönleri ve Senkronizasyon  
#### ✅ Cevap 152: Kanal kanalı (channel of channels)

Bu örnekte, birden fazla goroutine arasında iletişimi koordine etmek için kanal kanalı (channel of channels) kullanılmıştır. Her bir iç kanal bir tamsayı değeri taşır.

```go
package main
import "fmt"

func main() {
    kanalKanali := make(chan chan int)
    go func() {
        for i := 1; i <= 3; i++ {
            ch := make(chan int)
            kanalKanali <- ch
            go func(val int, c chan int) {
                c <- val * 10
            }(i, ch)
        }
        close(kanalKanali)
    }()
    for ch := range kanalKanali {
        fmt.Println("Alındı:", <-ch)
    }
}
```
