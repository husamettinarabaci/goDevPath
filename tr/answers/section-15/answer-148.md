## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 148: Kanal üzerinde range ile yineleme

Bu örnekte, bir kanal üzerinde `range` döngüsü kullanılarak kanal kapatılana kadar değerlerin nasıl alınacağı gösterilmiştir. Döngü, kanal kapatıldığında otomatik olarak sona erer.

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
    for val := range ch {
        fmt.Println("Alındı:", val)
    }
    fmt.Println("Kanal kapandı, alım tamamlandı.")
}
```
