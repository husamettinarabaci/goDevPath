## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ✅ Cevap 154: `sync.RWMutex` kullanımı

`sync.RWMutex`, birden fazla goroutine'in aynı anda veri okumasına izin verirken, yazma işlemi sırasında yalnızca bir goroutine'in erişimine izin verir. Okuyucular için `RLock`/`RUnlock`, yazıcılar için `Lock`/`Unlock` kullanılır.

```go
package main
import (
    "fmt"
    "sync"
    "time"
)

func main() {
    var (
        rw sync.RWMutex
        counter int
        wg sync.WaitGroup
    )
    // Yazıcılar
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func() {
            rw.Lock()
            counter++
            rw.Unlock()
            wg.Done()
        }()
    }
    // Okuyucular
    for i := 0; i < 10; i++ {
        wg.Add(1)
        go func() {
            rw.RLock()
            _ = counter // okuma simülasyonu
            time.Sleep(10 * time.Millisecond)
            rw.RUnlock()
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Son sayaç:", counter)
}
```
