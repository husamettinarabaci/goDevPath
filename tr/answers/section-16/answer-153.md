## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ✅ Cevap 153: Karşılıklı dışlama için `sync.Mutex` kullanımı

Birden fazla goroutine aynı veriye eriştiğinde yarış durumu oluşmaması için `sync.Mutex` kullanılır. Değişken güncellenmeden önce mutex kilitlenir, işlem bitince açılır. Böylece aynı anda sadece bir goroutine değişkeni değiştirebilir.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var (
        mu sync.Mutex
        sayac int
        wg sync.WaitGroup
    )
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            mu.Lock()
            sayac++
            mu.Unlock()
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Son sayaç:", sayac)
}
```
