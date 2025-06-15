## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ✅ Cevap 157: `sync.Map` kullanımı

`sync.Map`, birden fazla goroutine'in aynı anda güvenli şekilde kullanabileceği eşzamanlı bir harita (map) implementasyonudur.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var m sync.Map
    var wg sync.WaitGroup

    // Yazıcı goroutine'ler
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(i int) {
            m.Store(i, i*i)
            wg.Done()
        }(i)
    }

    // Okuyucu goroutine'ler
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(i int) {
            if v, ok := m.Load(i); ok {
                fmt.Printf("Anahtar: %d, Değer: %v\n", i, v)
            }
            wg.Done()
        }(i)
    }

    wg.Wait()

    // Tüm içerikleri yazdır
    m.Range(func(key, value any) bool {
        fmt.Printf("%v: %v\n", key, value)
        return true
    })
}
```
