## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Deadlock ve Yarış Durumları  
#### ✅ Cevap 158: Deadlock ve yarış durumu

Deadlock, goroutine'lerin birbirini beklemesiyle oluşur ve program ilerleyemez. Yarış durumu ise birden fazla goroutine'in ortak veriye senkronizasyon olmadan erişmesiyle oluşur.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    // Deadlock örneği
    ch1 := make(chan int)
    ch2 := make(chan int)
    go func() {
        ch1 <- 1 // alıcıyı bekler
        <-ch2    // değer bekler
    }()
    go func() {
        ch2 <- 2 // alıcıyı bekler
        <-ch1    // değer bekler
    }()
    // Aşağıdaki satırları açarsanız deadlock oluşur
    // time.Sleep(time.Second)

    // Yarış durumu örneği
    var x int
    var wg sync.WaitGroup
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            x++ // senkronizasyon yok, yarış durumu
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Yarış durumu sonucu:", x)
}
```
// Deadlock'u düzeltmek için buffered channel veya uygun senkronizasyon kullanın.
// Yarış durumunu düzeltmek için mutex veya atomic işlemler kullanın.
